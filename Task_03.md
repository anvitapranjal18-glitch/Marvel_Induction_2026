## **Task 3: Version Control Mastery — GitHub Workflows & Collaboration**

### **Description**

The core objective of this task was to move beyond basic Git commands and master the collaborative ecosystem of **GitHub**. This involved understanding the lifecycle of a contribution: from identifying tasks via **GitHub Issues**, to implementing changes in a localized environment, and finally submitting those changes through **Pull Requests (PRs)**. Additionally, the task focused on **GitHub Actions**, exploring how automated workflows can be used for Continuous Integration (CI) to validate code changes automatically upon submission.

### **Detailed Process**

- **Repository Exploration & Issue Identification:** I began by navigating to the official `UVCE-Marvel/git-task` repository. I spent time analyzing the **Issues** tab to understand how bugs and features are tracked. I learned how to "claim" a task and link my future work to a specific Issue ID to maintain a clean project history.
- **The Fork & Clone Workflow:** To ensure the main codebase remained stable, I created a **Fork** of the repository into my personal account. I then cloned this remote repository to my local machine using the CLI:
  ```bash
  git clone [https://github.com/](https://github.com/)[Your-Username]/git-task.git
  cd git-task
  ```
- **Branching & Atomic Commits:** I practiced "Feature Branching" to keep my workspace organized. Instead of working on the `main` branch, I created a dedicated branch for my task. I focused on making **Atomic Commits**—small, logical changes with descriptive messages that follow the "Conventional Commits" standard.
  ```bash
  git checkout -b feature/task-contribution
  git add .
  git commit -m "feat: updated readme with personal contributor details"
  ```
- **Pull Requests & Code Review:** After pushing my branch to GitHub, I initiated a **Pull Request (PR)**. I learned how to write a clear PR description, explaining _what_ was changed and _why_. I also observed how GitHub triggers **Automated Workflows (GitHub Actions)** to run linting and build tests on the PR before a maintainer reviews the code.
- **Syncing & Merge Conflict Resolution:** I practiced syncing my fork with the "Upstream" repository to ensure my local code was up to date. I gained experience in resolving **Merge Conflicts**—a critical skill for collaborative engineering when two developers modify the same line of code.

### **GitHub Feature Utilization**

| Feature            | Technical Purpose       | Role in Marvel Workflow                                           |
| :----------------- | :---------------------- | :---------------------------------------------------------------- |
| **Issues**         | Project Management      | Tracking tasks, bugs, and feature requests.                       |
| **Pull Requests**  | Code Collaboration      | Proposing changes and performing peer reviews.                    |
| **GitHub Actions** | CI/CD Automation        | Automatically testing code for errors on every push.              |
| **Forks**          | Distributed Development | Allowing users to experiment without affecting the original repo. |

### **Technical Skills Gained**

- **🛠️ Collaborative Git:** Transitioning from "solo" coding to a professional team-based workflow.
- **🤖 CI/CD Awareness:** Understanding how automated scripts (YAML) can be used to maintain code quality.
- **📂 Repository Management:** Learning to navigate complex project histories using the `git log` and `git blame` commands.
- **🤝 Peer Review Etiquette:** Gaining the ability to provide and receive constructive feedback during the code review process.

---
