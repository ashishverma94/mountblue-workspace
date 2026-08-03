# Review Questions

### 1) Initialize git repository

- `git init` command is used to initialize git repository in local folder
---

### 2) Add a file a.txt

- `touch a.txt` command is used to create file a.txt
---

### 3) Make a commit.

- `git add a.txt` stages it for next commit.
- `git commit -m "Create a.txt file"` this saves the staged changes as the first commit in the repo.
---

### 4) Create a branch called leaf

- `git checkout -b leaf` git checkout switches to existing branch and -b create new branch before switching to it.
---

### 5) Add a file b.txt

- `touch b.txt` command is used to create file b.txt
---

### 6) Create a second commit

- `git add b.txt` stages it for next commit.
- `git commit -m "Create b.txt file"` this saves the staged changes as the first commit in the repo.
- ---


### 7) Merge leaf into master

- `git checkout main` first go to main branch from leaf branch using this command
- `git merge leaf` merges the leaf branch into main.
- ---

### 8) What is staging area

- Staging area is a temporary area where git store changes before they are commited
- It is also called indexing. Files are placed in the staging area using command `git add`.
- ---

### 9) Where is the HEAD right now?

- HEAD is a pointer that refers current checked out branch or latest commit.
- `git branch` command is used to check the HEAD. The branch with * is the one that head is pointing to.
- ---

# Undoing Changes

### 1) Committed the wrong message?

- `git commit --amend -m "Create file b.txt"` use --amend before -m to change the message of latest commit and after -m write your new message.
- ---

### 2) Skipped file in the last commit?

- `git add <new file>` stage the missing file.
- `git commit --amend --no-edit` adds it to the previous commit without changing the commit message.
- ---

### 3) Accidentally committed on master?

- If we have accidentally committed on master and want to revert it then first switch to correct branch ( git checkout leaf). Now run command `git cherry-pick main` now leaf also has the commit of main. Then come to master branch ( git checkout master) and run command `git reset --hard HEAD~1`.
- ---








