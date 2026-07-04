# 🔒 Security & Vault

The **Secrets Vault** provides AES-256-GCM encryption for sensitive data stored in Max's memory.

## Encryption Model

| Property | Detail |
|---|---|
| **Algorithm** | AES-256-GCM (authenticated encryption) |
| **Key Derivation** | PBKDF2 with 100,000 iterations |
| **Salt** | 16-byte random (unique per device) |
| **IV** | 12-byte random (unique per encryption) |
| **Key Size** | 256-bit |
| **Storage** | Encrypted ciphertext only |
| **Password** | Never stored, never transmitted |

## How It Works

1. You set a **master password** when unlocking the vault
2. The password is combined with a random **salt** using **PBKDF2** (100,000 iterations)
3. This produces a 256-bit **AES key** that never leaves the session
4. Each secret value is encrypted with a unique **12-byte IV**
5. The ciphertext is stored in localStorage — raw values never touch disk
6. Locking the vault clears the derived key from memory

## Security Best Practices

- ✅ Use a **strong master password** (12+ chars, mixed case, symbols)
- ✅ **Lock the vault** when not in use
- ✅ **Export backups** before clearing browser data
- ❌ Never share your master password
- ❌ Never store master password in the same memory store
- ❌ Don't use the same password for vault that you use for other services

## What Can Be Stored

- API keys (OpenAI, Claude, etc.)
- Database connection strings
- JWT secrets
- Service tokens
- Personal access tokens

## What NOT to Store

- Master password itself (circular dependency!)
- Credit card numbers / banking data
- Passwords for critical accounts (use a dedicated password manager)

## Technical Notes

- Encryption/decryption is done via the **Web Crypto API** (SubtleCrypto)
- All operations are synchronous when using the UI; vault key is held in memory
- Closing the tab or locking the vault clears all derived keys
- Auto-backup saves **encrypted** vault data as well
