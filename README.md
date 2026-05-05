# AI Study Workflow Template

This repository provides a framework for using AI (specifically Claude Code) as a rigorous, personalized tutor integrated with an Obsidian knowledge vault. 

Instead of just asking an AI for answers, this workflow treats the AI as a pedagogical guide that manages your progress, tracks your weaknesses, and ensures you're actually learning the material.

## 🚀 The Workflow Architecture

### 1. The Knowledge Vault (Obsidian)
The workflow uses a hierarchical "Hub and Spoke" system:
- **Main Index**: The top-level entry point.
- **Hubs**: Broad category organizers (e.g., "Integration", "Organic Chemistry Basics").
- **Topics**: Detailed notes for specific concepts.
- **Sessions**: Dated logs (`YYYY-MM-DD.md`) that store the actual problems and solutions generated during a session.

### 2. The AI Tutor (Claude Code)
The AI is configured via a `CLAUDE.md` file to follow specific tutoring rules:
- **Hint-First Approach**: It will never give you the answer immediately.
- **Proof of Work**: It requires you to show your steps before confirming a solution.
- **Technical Rigor**: It uses strict LaTeX formatting for mathematical and technical expressions to ensure perfect rendering in Obsidian and Neovim.
- **Progressive Difficulty**: It manages a "Warmup $\rightarrow$ Easy $\rightarrow$ Medium $\rightarrow$ Hard $\rightarrow$ Challenge" progression.

## 🛠️ Setup Guide

### Step 1: Set Up Your Vault
1. Clone this repository or copy the `Template-Vault` folder into your Obsidian vault.
2. Use the `Prompts/obsidian-setup-prompt.md` with an AI to map your specific course syllabus to the Hubs and Topics structure.
3. Create your files based on the provided templates.

### Step 2: Configure Your AI Tutor
1. Copy `Prompts/CLAUDE.md` into the root of your project directory.
2. Replace `[Subject Name]` with the subject you are studying.
3. Start a session with Claude Code.

### Step 3: Start Learning
When you begin a session, the AI will ask you what you're studying and what your goals are. 
- **Tip**: Use a markdown preview (like the one in Obsidian or Neovim) to see the LaTeX equations render in real-time as the AI writes to your session files.

## 📖 Why This Works
By separating the **Knowledge** (the vault) from the **Interaction** (the session logs), you create a permanent record of your learning journey. The `CLAUDE.md` configuration prevents the AI from becoming a "cheat sheet" and turns it into a coach that pushes you to understand the *why* behind every answer.
# ai-tutor-setup
