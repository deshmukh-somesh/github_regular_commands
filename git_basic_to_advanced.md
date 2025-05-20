# Git Command Mastery Guide

## Table of Contents
1. [Essential Git Commands](#essential-git-commands)
2. [Practical Exercises](#practical-exercises)
3. [Git Interview Questions](#git-interview-questions)
4. [Advanced Git Techniques](#advanced-git-techniques)
5. [Best Practices](#best-practices)

## Essential Git Commands

### Repository Setup & Management

| Command | Description | Example |
|---------|-------------|---------|
| `git init` | Initializes a new Git repository | `git init` |
| `git clone <url>` | Creates a copy of a remote repository | `git clone https://github.com/username/repo.git` |
| `git remote add <name> <url>` | Connects local repo to a remote repository | `git remote add origin https://github.com/username/repo.git` |
| `git remote -v` | Lists all remote repositories | `git remote -v` |

### Basic Workflow Commands

| Command | Description | Example |
|---------|-------------|---------|
| `git status` | Shows the status of files in the working directory | `git status` |
| `git add <file>` | Adds file(s) to the staging area | `git add index.html` |
| `git add .` | Adds all changes to the staging area | `git add .` |
| `git commit -m "<message>"` | Records changes to the repository | `git commit -m "Add new feature"` |
| `git push <remote> <branch>` | Uploads local branch to remote repository | `git push origin main` |
| `git pull <remote> <branch>` | Fetches from and integrates with remote branch | `git pull origin main` |

### Branching & Merging

| Command | Description | Example |
|---------|-------------|---------|
| `git branch` | Lists all local branches | `git branch` |
| `git branch <name>` | Creates a new branch | `git branch feature-login` |
| `git checkout <branch>` | Switches to specified branch | `git checkout feature-login` |
| `git checkout -b <branch>` | Creates and switches to a new branch | `git checkout -b feature-login` |
| `git merge <branch>` | Merges specified branch into current branch | `git merge feature-login` |
| `git branch -d <branch>` | Deletes a branch | `git branch -d feature-login` |

### History & Differences

| Command | Description | Example |
|---------|-------------|---------|
| `git log` | Shows commit history | `git log` |
| `git log --oneline` | Shows compact commit history | `git log --oneline` |
| `git diff` | Shows changes between working dir and staging area | `git diff` |
| `git diff --staged` | Shows changes between staging area and last commit | `git diff --staged` |
| `git blame <file>` | Shows who changed what in a file | `git blame index.html` |

### Undoing Changes

| Command | Description | Example |
|---------|-------------|---------|
| `git restore <file>` | Discards changes in working directory | `git restore index.html` |
| `git restore --staged <file>` | Unstages a file | `git restore --staged index.html` |
| `git reset <commit>` | Moves branch pointer to specified commit | `git reset HEAD~1` |
| `git reset --hard <commit>` | Moves branch pointer and changes working dir | `git reset --hard HEAD~1` |
| `git revert <commit>` | Creates a new commit that undoes changes | `git revert a1b2c3d` |

### Stashing

| Command | Description | Example |
|---------|-------------|---------|
| `git stash` | Saves changes temporarily | `git stash` |
| `git stash list` | Lists all stashed changes | `git stash list` |
| `git stash apply` | Applies most recent stash | `git stash apply` |
| `git stash pop` | Applies and removes most recent stash | `git stash pop` |
| `git stash drop` | Removes most recent stash | `git stash drop` |

### Advanced Commands

| Command | Description | Example |
|---------|-------------|---------|
| `git rebase <branch>` | Reapplies commits on top of another branch | `git rebase main` |
| `git cherry-pick <commit>` | Applies a specific commit to current branch | `git cherry-pick a1b2c3d` |
| `git tag <name>` | Creates a new tag at current commit | `git tag v1.0.0` |
| `git fetch <remote>` | Downloads objects from remote without merging | `git fetch origin` |
| `git bisect` | Uses binary search to find which commit introduced a bug | `git bisect start/bad/good` |

## Practical Exercises

### Exercise 1: Setting Up a New Repository
1. Create a new directory for your project
2. Initialize a Git repository
3. Create a new file called `README.md`
4. Add and commit the file
5. Create a repository on GitHub
6. Add the remote repository
7. Push your changes to GitHub

```bash
mkdir my-project
cd my-project
git init
echo "# My Project" > README.md
git add README.md
git commit -m "Initial commit"
git remote add origin https://github.com/username/my-project.git
git push -u origin main
```

### Exercise 2: Branching and Merging
1. Create a new branch called `feature-a`
2. Make changes to a file
3. Commit your changes
4. Switch back to the main branch
5. Merge the feature branch
6. Delete the feature branch

```bash
git checkout -b feature-a
echo "New feature added" >> README.md
git add README.md
git commit -m "Add new feature"
git checkout main
git merge feature-a
git branch -d feature-a
```

### Exercise 3: Resolving Merge Conflicts
1. Create two branches from main: `feature-x` and `feature-y`
2. In each branch, modify the same line in the same file
3. Commit changes in both branches
4. Merge one branch into main
5. Try to merge the second branch and resolve the conflict

```bash
git checkout -b feature-x
echo "Feature X" > shared.txt
git add shared.txt
git commit -m "Add Feature X"

git checkout main
git checkout -b feature-y
echo "Feature Y" > shared.txt
git add shared.txt
git commit -m "Add Feature Y"

git checkout main
git merge feature-x
git merge feature-y
# Resolve conflict manually
git add shared.txt
git commit -m "Merge feature-y with resolved conflicts"
```

### Exercise 4: Undoing Changes
1. Make changes to a file and stage them
2. Unstage the changes
3. Make different changes and commit them
4. Revert the commit
5. Make new changes, commit, then reset to the previous commit

```bash
echo "Some text" > file.txt
git add file.txt
git restore --staged file.txt

echo "Different text" > file.txt
git add file.txt
git commit -m "Add different text"

git revert HEAD

echo "New text" > file.txt
git add file.txt
git commit -m "Add new text"
git reset --hard HEAD~1
```

### Exercise 5: Working with Remote Repositories
1. Clone an existing repository
2. Create a new branch
3. Make changes and commit them
4. Push the branch to the remote repository
5. Create a pull request (on GitHub)
6. Review and merge the pull request

```bash
git clone https://github.com/username/repository.git
cd repository
git checkout -b new-feature
echo "New feature code" > feature.txt
git add feature.txt
git commit -m "Implement new feature"
git push -u origin new-feature
# Go to GitHub and create a pull request
```

## Git Interview Questions

### Basic Questions

1. **What is Git?**
   - Git is a distributed version control system that tracks changes in source code during software development, enabling multiple developers to work together on a project.

2. **How is Git different from other version control systems like SVN?**
   - Git is distributed (each developer has a full copy of the repository), while SVN is centralized.
   - Git stores snapshots of files, not just differences.
   - Git operations are mostly local, making them faster.
   - Git has better branching and merging capabilities.

3. **What is a repository in Git?**
   - A repository is a data structure that stores metadata and objects for a project, containing all files and the complete history of changes.

4. **What is the difference between Git and GitHub?**
   - Git is a version control system.
   - GitHub is a cloud-based hosting service for Git repositories that provides additional collaboration features like pull requests, issues, and project management tools.

5. **What are the stages of Git?**
   - Working directory: Where files are modified
   - Staging area (index): Where changes are prepared for commit
   - Local repository: Where committed changes are stored

6. **Explain the basic Git workflow.**
   - Modify files in the working directory
   - Stage changes using `git add`
   - Commit changes using `git commit`
   - Push changes to remote using `git push`

7. **What is a commit in Git?**
   - A commit is a snapshot of your repository at a specific point in time, including a reference to the parent commit(s), author information, timestamp, and a message describing the changes.

8. **What is a branch in Git?**
   - A branch is a lightweight, movable pointer to a commit, allowing parallel development without affecting the main codebase.

### Intermediate Questions

9. **What is the difference between `git pull` and `git fetch`?**
   - `git fetch` downloads changes from the remote repository but doesn't integrate them into your working files.
   - `git pull` is effectively `git fetch` followed by `git merge`, downloading and integrating changes.

10. **What is a merge conflict in Git and how do you resolve it?**
    - A merge conflict occurs when Git cannot automatically resolve differences between branches, typically when the same lines in the same file have been modified.
    - To resolve:
      - Git marks the conflicted areas in the file
      - Manually edit the file to resolve conflicts
      - Stage the resolved file with `git add`
      - Complete the merge with `git commit`

11. **What is rebasing in Git?**
    - Rebasing is the process of moving or combining a sequence of commits to a new base commit, creating a linear project history.

12. **What's the difference between `git merge` and `git rebase`?**
    - `git merge` creates a new merge commit that combines changes from both branches, preserving history.
    - `git rebase` rewrites commits from one branch onto another, creating a linear history but altering commit history.

13. **How would you undo the last commit in Git?**
    - To keep the changes but undo the commit: `git reset HEAD~1`
    - To discard changes and undo the commit: `git reset --hard HEAD~1`
    - To create a new commit that undoes changes: `git revert HEAD`

14. **What is `git stash` used for?**
    - `git stash` temporarily shelves changes in your working directory so you can switch to another task, then return and reapply them later.

15. **How do you create and apply a patch in Git?**
    - Create: `git diff > changes.patch` or `git format-patch`
    - Apply: `git apply changes.patch` or `git am`

### Advanced Questions

16. **What is a detached HEAD state in Git?**
    - A detached HEAD occurs when you check out a specific commit instead of a branch, pointing HEAD directly to a commit rather than a branch reference.

17. **What is Git bisect and how would you use it?**
    - `git bisect` helps find which commit introduced a bug using binary search.
    - Process:
      - Start with `git bisect start`
      - Mark the current version as bad: `git bisect bad`
      - Mark a known good version: `git bisect good <commit>`
      - Git checks out middle commit
      - Mark each tested commit as good/bad
      - Git eventually identifies the first bad commit

18. **How would you squash multiple commits into one?**
    - Using interactive rebase:
      ```bash
      git rebase -i HEAD~n  # n is the number of commits to consider
      # Mark commits as 'squash' or 's' in the editor
      # Edit the combined commit message
      ```

19. **Explain Git hooks.**
    - Git hooks are scripts that run automatically when certain Git events occur (pre-commit, post-commit, pre-push, etc.).
    - They can be used for enforcing coding standards, running tests, or triggering deployment.

20. **What is the difference between a bare and non-bare repository?**
    - A bare repository (created with `git init --bare`) has no working directory and is typically used on servers.
    - A non-bare repository has a working directory and is used for development.

21. **How does Git store data internally?**
    - Git uses a content-addressable filesystem with four types of objects:
      - Blob: File content
      - Tree: Directory content
      - Commit: Snapshot with metadata
      - Tag: Named reference to a commit

22. **How would you recover a deleted branch in Git?**
    - Find the commit hash using `git reflog`
    - Create a new branch pointing to that commit: `git branch <branch-name> <commit-hash>`

## Advanced Git Techniques

### Git Workflows

1. **Git Flow**
   - Uses two main branches (main/master and develop)
   - Feature, release, and hotfix branches
   - Good for projects with scheduled releases

2. **GitHub Flow**
   - Single main branch (main/master)
   - Feature branches created from main
   - Pull requests for code review
   - Simple and ideal for continuous delivery

3. **GitLab Flow**
   - Combines Git Flow and GitHub Flow
   - Environment branches (production, staging, etc.)
   - Uses feature branches and merge requests

### Useful Git Aliases

Set up time-saving aliases:

```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.unstage 'restore --staged'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual '!gitk'
```

### Interactive Rebase

Manipulate commit history with interactive rebase:

```bash
git rebase -i HEAD~5  # Consider last 5 commits
```

Options in interactive rebase:
- `pick`: Keep the commit
- `reword`: Change the commit message
- `edit`: Amend the commit
- `squash`: Combine with previous commit
- `fixup`: Combine with previous commit (discard message)
- `drop`: Remove the commit

### Reflog

Recover lost commits or reset mistakes:

```bash
git reflog  # Show reference logs
git checkout HEAD@{2}  # Go back to where HEAD was 2 moves ago
git reset --hard HEAD@{2}  # Reset to 2 moves ago
```

### Submodules and Subtrees

Manage external dependencies:

**Submodules**:
```bash
git submodule add <repository> <path>
git submodule update --init --recursive
```

**Subtrees**:
```bash
git subtree add --prefix=<path> <repository> <ref> --squash
git subtree pull --prefix=<path> <repository> <ref> --squash
```

## Best Practices

### Commit Messages

1. Use a concise subject line (50 chars or less)
2. Separate subject from body with a blank line
3. Use imperative mood in the subject ("Add feature" not "Added feature")
4. Explain what and why, not how
5. Reference issues or tickets where applicable

Example:
```
Add user authentication feature

- Implement login/logout functionality
- Add password reset capability
- Store user sessions securely

Fixes #123
```

### Branching Strategy

1. Keep the main branch stable and deployable
2. Create descriptive branch names (feature/login, bugfix/header-display)
3. Regularly sync with the main branch
4. Delete branches after merging
5. Consider using prefixes for branch types (feature/, bugfix/, hotfix/, etc.)

### Repository Maintenance

1. Use `.gitignore` files to exclude unnecessary files
2. Periodically clean up old branches
3. Consider using Git LFS for large files
4. Regularly gc (garbage collect): `git gc`
5. Compress the repository: `git repack -a -d --depth=250 --window=250`

### Collaboration

1. Pull before you push
2. Use pull requests/merge requests for code review
3. Keep commits atomic and focused on a single task
4. Rebase feature branches before merging
5. Tag important releases with semantic versioning

### Security

1. Never commit sensitive data (passwords, API keys, etc.)
2. Use signed commits for verification
3. Restrict access to main branches
4. Perform regular backups
5. Consider using pre-commit hooks to prevent sensitive data leaks