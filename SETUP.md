# Environment Setup Protocol

This repository is the **Single Source of Truth** for the Gemini CLI environment. Any machine syncing this repository *must* adhere to the following protocol to ensure absolute state continuity and transparency.

## 1. Mandatory Startup Sync (NON-NEGOTIABLE)
Before any Gemini CLI operation, the environment must ensure its local state is identical to the `origin/main` branch. A `git pull` must precede every session.

## 2. Startup Transparency Banner
Every Gemini CLI initialization MUST explicitly print: 
`--- [INFO] Gemini CLI Configuration loaded from <PATH> at commit <HASH> (customized for Thomas) ---`

## 3. Implementation
To automate these mandates, use the version-controlled wrapper scripts located in the `scripts/` directory.

### macOS (Zsh)
Add the following to `~/.zshrc`:
```bash
alias gemini="bash $HOME/projects/gemini-config/scripts/gemini-wrapper.sh"
```

### Windows (PowerShell)
Add the following to your PowerShell profile (`$PROFILE`):
```powershell
function gemini { & "C:\Users\<YourUser>\projects\gemini-config\scripts\gemini-wrapper.ps1" $args }
```

*Note: Update `<YourUser>` to match your local Windows username.*
