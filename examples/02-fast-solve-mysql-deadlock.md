# ⚡ Example: Debugging a MySQL Deadlock

> **Mode**: Fast Solve | **Platform**: Any

## Before Max

```
User: "My DB is returning a deadlock error, help"

Chat: "You might have a deadlock. Check your transaction order."
```

## After Max

Max activates **Fast Solve mode**, performs root cause analysis, provides the exact query to diagnose, and a fix:

```
User: "I'm getting 'Deadlock found when trying to get lock; try restarting transaction' in MySQL"

Max: [mode: fast-solve | score: 8 | alt: code: 2]

🎯 Bottom Line: Two concurrent transactions locking rows in opposite order cause the deadlock.

🔍 Root Cause:
Transaction A: UPDATE accounts SET balance=? WHERE id=1 → UPDATE accounts SET balance=? WHERE id=2
Transaction B: UPDATE accounts SET balance=? WHERE id=2 → UPDATE accounts SET balance=? WHERE id=1
When both run simultaneously → A locks row 1, B locks row 2 → mutual wait → deadlock.

💻 Diagnosis:
```sql
-- Check recent deadlocks
SHOW ENGINE INNODB STATUS\G
-- Look for "LATEST DETECTED DEADLOCK" section
-- Shows which transactions were involved and which query caused the conflict
```

💻 The Fix:
```sql
-- Apply a consistent lock order across ALL transactions
-- Always lock lower ID first, higher ID second:

-- ✅ Correct: Same order everywhere
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;  -- Always 1 first
UPDATE accounts SET balance = balance + 100 WHERE id = 2;  -- Then 2
COMMIT;

-- Or use SELECT ... FOR UPDATE in application code to enforce order:
START TRANSACTION;
SELECT * FROM accounts WHERE id IN (1, 2) ORDER BY id FOR UPDATE;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

💡 Max's Tip: The real root cause is not the deadlock itself — it's the inconsistent ordering. Fix the ordering, and deadlocks vanish.

✅ Next Steps:
1. Audit all UPDATE queries for consistent lock ordering
2. Add retry logic (3 attempts with exponential backoff) for remaining edge cases
3. Set innodb_lock_wait_timeout = 5 (seconds) to fail fast instead of hanging
4. Monitor with SHOW ENGINE INNODB STATUS periodically
```
