# Edge Gallery Agent Skill Hosting Guide

## GitHub Pages Setup

### 1. Create Repo Structure
```
your-skill/
├── .nojekyll              # CRITICAL: prevents Jekyll from converting .md files
├── README.md              # Documentation (English recommended for OSS)
└── skill-name/
    └── SKILL.md           # The persona file with YAML frontmatter
```

### 2. GitHub Pages Configuration
- **Build type**: Use `legacy` (NOT `workflow`)
  - `workflow` requires a `.github/workflows/pages.yml` file
  - `legacy` serves files directly from the branch
- **Source**: `main` branch, root `/`
- **.nojekyll**: Empty file in repo root — disables Jekyll processing

### 3. API Commands
```bash
# Enable Pages (legacy mode)
curl -X POST "https://api.github.com/repos/$USER/$REPO/pages" \
  -H "Authorization: Bearer $TOKEN" \
  -d '{"source":{"branch":"main","path":"/"}}'

# Update repo
curl -X PATCH "https://api.github.com/repos/$USER/$REPO" \
  -H "Authorization: Bearer $TOKEN" \
  -d '{"description":"...","homepage":"https://$USER.github.io/$REPO/skill-name/"}'

# Add topics
curl -X PUT "https://api.github.com/repos/$USER/$REPO/topics" \
  -H "Authorization: Bearer $TOKEN" \
  -d '{"names":["agent-skill","edge-gallery","gemma-4","universal-agent"]}'
```

### 4. URL for Edge Gallery App
- **Correct**: `https://$USER.github.io/$REPO/skill-name/`
- **Wrong**: `https://$USER.github.io/$REPO/skill-name/SKILL.md`
- The app appends `SKILL.md` automatically

### 5. SKILL.md Format Requirements
- YAML frontmatter with `---` delimiters (start AND end)
- **Required fields**: `name` (kebab-case), `description`
- **Optional**: `metadata` with `require-secret`, `require-secret-description`
- Body is markdown instructions for the LLM

### 6. Token Requirements
- **Classic PAT** (starts with `ghp_`): needs `repo` scope for repo creation + push
- **Fine-grained PAT** (starts with `github_pat_`): needs `Administration: write` permission for repo creation
- Fine-grained tokens without repo creation scope can still push to existing repos

### 7. Pitfalls
- ❌ Pushing PAT in commit → GitHub blocks push (secret scanning)
  - Fix: `git reset --hard <clean-commit>`, rewrite the commit without the token
  - Or visit the unblock URL GitHub provides
- ❌ `build_type: "workflow"` without a workflow file → 404 on Pages
  - Fix: Use `legacy` or add `.github/workflows/pages.yml`
- ❌ No `.nojekyll` → GitHub Pages converts .md files to .html
- ❌ URL with `SKILL.md` suffix → app tries `SKILL.md/SKILL.md`
  - Fix: Use the folder URL only

### 8. JS Scripts (Optional Tools)

For platforms that support `run_js` (Edge Gallery), include scripts under `scripts/`:

```
skill-name/
└── scripts/
    ├── memory.html      # 🔒 Persistent KV store + AES vault + auto-backup
    ├── search.html      # 🌐 Web search (CORS proxy)
    ├── vision.html      # 👁️ Image color/texture analysis
    ├── voice.html       # 🎤 Text-to-Speech (Web Speech API)
    └── dashboard.html   # 📊 Stats viewer (3 themes)
```

Scripts must be self-contained HTML files (CSS + JS inline). They use `localStorage` for persistence and Web APIs (Canvas, SpeechSynthesis, fetch) — no external dependencies. The SKILL.md should include a "JS Tools" section with the `run_js` payload format for each script.

### 9. Verification
```bash
# Check if deployed
curl -s -o /dev/null -w "%{http_code}" "https://$USER.github.io/$REPO/skill-name/SKILL.md"
# 200 = deployed, 404 = not yet
```
