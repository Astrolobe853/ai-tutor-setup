# Terminal-Based AI Study Workflow

A framework for using **Claude Code** as a rigorous, personalized tutor,
integrated with an Obsidian knowledge vault.

Instead of asking an AI for answers, this workflow treats it as a
**pedagogical coach**. One that manages your progress, tracks your
weaknesses, and ensures you're actually learning the material.

<img width="2557" height="1397" alt="Image" src="https://github.com/user-attachments/assets/3e22e35f-43e5-4a1a-bf9e-4ff13a9b065e" />

---

## Why This Works

Most people use AI as a search engine. This workflow uses it as a tutor
that enforces three rules:

- **Hint-first**: It will never give you the answer immediately
- **Proof of work**: You must show your steps before any solution is confirmed
- **Progressive difficulty**: Every session scales from warmup → easy → medium → hard → challenge

By separating your **knowledge** (the vault) from your **interactions**
(session logs), you build a permanent, searchable record of your learning.
`CLAUDE.md` prevents the AI from becoming a cheat sheet and turns it into
a coach that pushes you to understand the *why* behind every answer.

---

## Requirements

- [Claude Code](https://claude.ai/code) (or any AI CLI)
- [Obsidian](https://obsidian.md/) for the knowledge vault
- [Neovim](https://neovim.io/) 0.9+ with `markdown-preview.nvim` *(optional but recommended)*
- Node.js & npm *(for markdown-preview.nvim)*

---

## Architecture

The workflow has two components that work together:

### 1. The Knowledge Vault (Obsidian)

A hierarchical **Hub and Spoke** system:

| Layer | Purpose | Example |
|---|---|---|
| **Main Index** | Top-level entry point | `Index.md` |
| **Hubs** | Broad category organizers | `Integration.md`, `Organic Chemistry.md` |
| **Topics** | Detailed concept notes | `U-Substitution.md` |
| **Sessions** | Dated problem/solution logs | `2026-05-05.md` |

Session files are written by the AI in real-time during your tutoring
session, giving you a permanent log of every problem you've worked through.

### 2. The AI Tutor (`CLAUDE.md`)

The AI is configured via a `CLAUDE.md` file placed in your project root.
Claude Code reads this automatically at the start of every session.

Key behaviours it enforces:

- **Hint-first approach** — never gives answers immediately
- **Proof of work** — requires you to show steps before confirming
- **Strict LaTeX formatting** — all math renders correctly in Obsidian and Neovim
- **Weak area tracking** — maintains a running list of topics to revisit
- **Progressive difficulty** — warmup → easy → medium → hard → challenge

---

## Setup Guide

### Step 1 — Requirements

Make sure you have Claude Code and Obsidian installed before continuing.

### Step 2 — Set Up Your Vault

1. Clone this repository and copy the `Template-Vault/` folder into your
   Obsidian vault directory
2. Add your course materials (lecture notes, textbook PDFs, past exams)
   to the relevant Hub folders
3. Use `Prompts/obsidian-setup-prompt.md` with an AI to map your course
   syllabus to the Hub and Topic structure automatically
4. Create your topic files using the provided templates

### Step 3 — Configure Your Tutor

1. Copy `Prompts/CLAUDE.md` into the **root of your project directory**
2. Replace all `[Subject Name]` placeholders with your subject
3. Add a **Weak Areas** section — instruct Claude to update it
   automatically as gaps are discovered during sessions
4. Launch Claude Code from the same directory:

```bash
cd your-project/
claude
```

### Step 4 — Start a Session

Claude will open by asking what you're studying and what your goals are
for the session. From there it manages the rest.

> **Tip:** Open your session file (`Sessions/YYYY-MM-DD.md`) in Neovim
> with `:MarkdownPreview` running so you see LaTeX equations render
> in real-time as the AI writes them.

---

## Recommended Neovim Setup

For the best experience, use Neovim with a live markdown preview:

1. Install [lazy.nvim](https://github.com/folke/lazy.nvim) as your plugin manager
2. Add `markdown-preview.nvim` to your `init.lua`:

```lua
{
  "iamcco/markdown-preview.nvim",
  build = "cd app && npm install",
  ft = { "markdown" },
  config = function()
    vim.g.mkdp_auto_start = 0
    vim.g.mkdp_theme = 'dark'
  end,
}
```

3. Split your workspace: session file in Neovim, live preview in a browser tab

KDE users: use Meta + arrow keys to tile Konsole and the browser side by side.

---

## Optional: Local LLMs with Ollama

If you prefer to run a model locally for privacy or offline access:

1. Install [Ollama](https://ollama.com/)
2. Pull a model:
```bash
ollama run llama3
# or
ollama run mistral
```
3. Point your AI CLI to the local Ollama endpoint

> ⚠️ **Note:** Local models are free and private, but significantly weaker
> than Claude for rigorous STEM tutoring — especially for multi-step proofs,
> calculus, and chemistry. Expect more errors and less pedagogical structure.
> Recommended only if privacy or cost is a hard constraint.

---

## Roadmap

- [ ] Google Classroom / D2L scraper to auto-populate vault with course material
- [ ] Session summary auto-generator (weekly review notes)
- [ ] Anki flashcard export from session logs
- [ ] Multi-subject CLAUDE.md templates (Calculus, Organic Chemistry, Physics)

---

## Repository Structure
.\
├── README.md\
├── CLAUDE.md                  # AI tutor configuration (template)\
├── Template-Vault/\
│   ├── Index.md\
│   ├── Hubs/\
│   ├── Topics/\
│   └── Sessions/\
├── Prompts/\
│   ├── CLAUDE.md\
│   └── obsidian-setup-prompt.md\
└── nvim/\
└── init.lua               # Neovim config\

---

## Contributing

Contributions welcome especially CLAUDE.md templates for other subjects.
Open a PR or file an issue if you have ideas.

---
