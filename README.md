XYZ - MERN Project: VS Code + GitHub (Quick Paste)

Purpose:
A compact, ready-to-paste README text explaining how to work with the XYZ MERN project using VS Code and GitHub. Copy this whole file and paste into your GitHub README or save as README.txt.

Prerequisites:
- VS Code installed
- Git installed and configured (git config --global user.name "Your Name"; git config --global user.email "you@example.com")
- GitHub account

Open project in VS Code:
- From terminal:
  cd XYZ
  code .

Initialize Git (one-time):
- In project root:
  git init
- Create .gitignore (add node_modules, .env, build folders, etc.)

Suggested .gitignore (paste into .gitignore):
node_modules/
.env
client/node_modules/
client/build/
server/node_modules/
*.log
.DS_Store

First commit:
git add .
git commit -m "Initial project structure: client + server folders"

Create GitHub repo (via web) and connect:
- On GitHub: New repository → name: XYZ → create (do NOT initialize with README)
- Then in terminal:
  git remote add origin https://github.com/yourname/XYZ.git
  git branch -M main
  git push -u origin main

(Alternative using GitHub CLI if installed)
gh repo create yourname/XYZ --public --source=. --remote=origin --push

Daily small-change workflow (recommended):
# check status
git status
# stage specific files or all
git add .
# commit with short, meaningful message
git commit -m "feat: add login API" 
# push to remote
git push

Quick commit message style:
- Use prefixes: feat:, fix:, chore:, docs:, refactor:, test:
- Example: "feat: add user auth routes" or "fix: correct CORS header"

Working with branches (recommended):
# create feature branch
git checkout -b feature/login
# do work, commit locally
git add .
git commit -m "feat(login): add frontend login form"
# push branch
git push -u origin feature/login
# open PR on GitHub → review → merge to main

Using VS Code UI for Git:
- Open Source Control icon (left sidebar)
- Stage changes by clicking + or file
- Write commit message in top box → click ✔ to commit
- Click "..." → Push / Pull / Sync
- Use GitLens extension for rich blame/history info

Handling .env securely:
- Never push .env. Add it to .gitignore.
- Create a .env.example with keys but no secrets and push that:
  MONGO_URI=
  PORT=5000

If you want to push only part of the project (e.g., server changes):
git add server/
git commit -m "chore(server): update README for API"
git push

Undo / revert:
- Undo last commit but keep changes staged:
  git reset --soft HEAD~1
- Revert a pushed commit safely:
  git revert <commit-hash>

Merge conflicts (basic):
- Pull latest: git pull
- If conflict occurs, open conflicted files in VS Code → use inline merge editor → choose changes and save
- After resolving:
  git add <files>
  git commit
  git push

Recommended VS Code extensions:
- GitLens — super helpful for history/blame
- Prettier & ESLint — format & lint
- GitHub Pull Requests and Issues — create/manage PRs inside VS Code
- REST Client or Thunder Client — test APIs locally

Tips:
- Commit often, push small changes frequently.
- Use clear commit messages.
- Use feature branches for larger items and open PRs to merge into main.
- Keep server and client config separate (.env for server, .env for client if needed).
- If you want a single command to run both client and server locally, use concurrently (install in root or use npm scripts).

Example small workflow to add a new feature:
1) git checkout -b feat/signup
2) make changes in client/ and server/
3) git add .
4) git commit -m "feat(signup): add signup frontend + API"
5) git push -u origin feat/signup
6) Open PR on GitHub and merge after review

That's it — copy this file content into your repo README or save as README.txt and keep it as your quick-reference for VS Code + GitHub workflow.

Good luck! 💪
