Step by Step Process: VERSION CONTROL SYSTEM (VCS) 

Phase 1: Repository Setup
Create the Repo: Go to GitHub and create a public repo named Frontend-version-control-task-[yourname].

Initialize locally:

git init
echo "# Frontend Version Control Task" > README.md
git add README.md
git commit -m "Initial commit: Add README"
git remote add origin https://github.com/[your-username]/[your-repo-name].git
git branch -M main
git push -u origin main
Phase 2: Branching & Collaboration
You need to create two features. Let's do a Header and a Footer.

Feature 1: Header

git checkout -b feature-header
# Make 3 changes/commits (e.g., create header.html, add styles, add logo)
touch header.html
git add . && git commit -m "feat: add basic header structure"
echo "<header>My Site</header>" >> header.html
git add . && git commit -m "feat: add site title to header"
# ... add one more commit ...
git push origin feature-header
Feature 2: Footer

git checkout main
git checkout -b feature-footer
# Repeat 3 commits for the footer...
git push origin feature-footer
Phase 3: Pull Requests & Merging
Go to GitHub. You will see "Compare & pull request" buttons.

Open PRs: Create a PR for feature-header -> main.

Simulate Review: Go to the "Files changed" tab in the PR, click a line of code, and leave a comment like "Consider using a <nav> tag here."

Merge: Click "Merge pull request" and "Confirm merge."

Phase 4: Reversion & Cleanup
This is the part most students find tricky. Here is how to do it:

1. Reverting a commit:

# Make an "error"
echo "This is a bug" >> bug.txt
git add . && git commit -m "feat: add intentional bug"
# Revert it (This creates a new commit that undoes the previous one)
git revert HEAD
2. Rename a branch:

# Rename locally
git branch -m feature-footer footer-final
# Update the remote (delete old, push new)
git push origin --delete feature-footer
git push origin footer-final

SUMMARY :

### Branches
- `feature-header`: Created the top navigation bar.
- `footer-final`: Created the site footer (renamed from feature-footer).

### Commands Used Frequently
- `git checkout -b`: Create and switch branches.
- `git commit -m`: Save changes with a message.
- `git push`: Upload local changes to GitHub.
- `git revert`: Undo an error safely.

### Lessons Learned
- Always pull the latest `main` before starting a new branch.
- Meaningful commit messages make debugging much easier.
