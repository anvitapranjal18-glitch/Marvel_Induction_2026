# Task 3: GitHub Integrated Workflows

---

### 1. Objective
To master the professional software development lifecycle, focusing on local development, version control with Git, and collaborative tools like Pull Requests and GitHub Actions.

### 2. Workflow Implemented
1.  **Repository Forking:** Created a personal copy of the `UVCE-Marvel/git-task` repository to work independently.
2.  **Local Development:** Cloned the repository to a local machine and used the terminal for version control.
3.  **Bug Identification:** Discovered a logic error in `main.py` where the addition function was incorrectly adding a constant value of 1.
4.  **Version Control:** Executed `git add`, `git commit`, and `git push` to manage changes.
5.  **Collaboration:** Submitted a Pull Request (PR) to merge the bug fix back into the main UVCE-Marvel repository.

---

### 3. Visual Evidence (Task 3 Proofs)

#### A. Terminal Operations & Git Commands
*Demonstrating the use of Git CLI to clone, commit, and push changes from a MacBook Pro terminal.*
![Terminal Proof](./marvel-github-4.jpg)

#### B. The Bug Fix (Code Diff)
*Showing the exact logic change in `main.py`: removing the unnecessary `+ 1` from the return statement.*
![Code Fix Proof](./marvel%20github-3.jpg)

#### C. Commit History
*A record of the iterative changes made to resolve the addition function bug.*
![Commit Proof](./marvel%20github-2.jpg)

#### D. Official Pull Request
*The final submission of the fixed code to the UVCE-Marvel organization (PR #247).*
![PR Proof](./Marvel-github.jpg)

---

### 4. Challenges & Solutions
* **Challenge:** Ensuring the local commits were properly pushed to the correct remote branch.
* **Solution:** Verified the remote origin using `git remote -v` and ensured the branch tracking was correctly set to `main`.
* **Challenge:** Passing the automated GitHub Actions checks.
* **Solution:** By removing the `+ 1` logic error, the automated test suite was able to validate the function correctly.