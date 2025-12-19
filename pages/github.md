---
layout: default
title: GitHub Primer
description: Getting started with Git and GitHub
---

# GitHub Primer
This primer is designed to help you get started with Git and GitHub, two essential tools for software development and collaboration. By the end of this lesson, you will be able to create, clone, and manage repositories, synchronize changes, and collaborate effectively using GitHub. We will also explore how to use GitHub Actions for automation and AI-powered development tools like GitHub Copilot.

> **Note:** Throughout this guide, you may see references to both `main` and `master` as the default branch name. New repositories on GitHub use `main` by default, but some older repositories use `master`. You can check your branch name with `git branch` command.

### Introduction: Git and GitHub
* [Git](https://git-scm.com/) is a popular software development tool.
* Used by developers to collaborate and version control code.   
* A collaborative environment to develop written works including code!
* [GitHub](https://www.github.com) is popular for online git repository hosting
  - Free for open source  
  - [BitBucket](https://bitbucket.org/), is another such a service.

### Prerequisite lessons
- Lots of curiosity
- [Linux Commands](https://www.cheatography.com/davechild/cheat-sheets/linux-command-line/pdf/). These directory operations will be handy:

```bash
# Directory Operations
pwd # Show current directory
mkdir dir # Make directory dir
cd dir # Change directory to dir
cd .. # Move up a directory
ls  # list files and directories in the current directory
```

# Lesson goals
- Create, clone and manage online repositories
- Create and manage local repositories
- Synchronize repositories
- Collaborate using GitHub

# Materials required
- Download and install [git](https://git-scm.com/download/)
- Download and install [Visual Studio Code (VS Code)](https://code.visualstudio.com/)

# Table of Contents    
<!-- TOC START min:1 max:3 link:true update:true -->
- [GitHub Primer](#github-primer)
    - [Step 1: Create an Account](#step-1-create-an-account)
    - [Step 2: Hello World](#step-2-hello-world)
    - [Step 3: Clone a Repository](#step-3-clone-a-repository)
    - [Step 4: Push Changes](#step-4-push-changes)
    - [Step 5: Pull Remote Changes](#step-5-pull-remote-changes)
    - [Step 6: Fork a Repository](#step-6-fork-a-repository)
    - [Step 7: Markdown](#step-7-markdown)
    - [Step 8: Project Management](#step-8-project-management)
    - [Step 9: AI-Powered Development](#step-9-ai-powered-development)
    - [Step 10: Automate Your Workflow with GitHub Actions](#step-10-automate-your-workflow-with-github-actions)
    - [Fork This Course](#fork-this-course)
    - [Cybersecurity Reflections](#cybersecurity-reflections)
- [Additional Resources](#additional-resources)
- [Acknowledgements](#acknowledgements)
- [License](#license)
<!-- TOC END -->

# Step 1: Create an Account
First things first, create a free account on GitHub. [https://github.com/join](https://github.com/join)
You will also need to verify your email address after registration to use your new GitHub account.

[Top](#table-of-contents)

# Step 2: Hello World
Complete the following GitHub tutorial:
[https://guides.github.com/activities/hello-world/](https://guides.github.com/activities/hello-world/)

> **Tip:** The `hello-world` repository you create in this step will be used throughout the rest of this guide for hands-on practice.

At the end of Step 2, you will have created a `remote` repository and will have added a `branch`. It is `remote` because all your files are on the GitHub server. As a developer, you might ask, _"how do I use this to manage my local codebase if it is just online?"_ It is not convenient to write and test code online, especially when many applications require locally installed packages to work. Using your own `Local` repository would be great. We will do just that in the next step.   

Git is a distributed configuration management system. Unlike a centralized code repository, there is no single authoritative repository. With Git you can have multiple independent repositories that could be in different states at any given time. If needed, these repositories may be synchronized with reference to commits.

[Top](#table-of-contents)

# Step 3: Clone a Repository

Cloning a repository allows you to create a local copy of a remote project from GitHub onto your computer. This is the most common way to start working with an existing project, contribute to open source, or collaborate with others.

## Why Clone a Repository?
- To work on a project locally, with full access to all files and history.
- To contribute changes, experiment, or customize code.
- To keep your local copy in sync with the remote repository.

## Example Scenario
Suppose you want to work on the `hello-world` repository you created on GitHub. Cloning it will let you edit files, run code, and track changes on your own computer.

## Step-by-Step Instructions

1. **Check if Git is Installed**
   - Open your terminal (PowerShell on Windows, Terminal on Mac/Linux).
   - Run:
     ```bash
     git --version
     ```
   - If you see a version number, Git is installed. If not, [install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

2. **Get the Repository URL**
   - On GitHub.com, navigate to your repository (e.g., `hello-world`).
   - Click the green `<> Code` button and copy the HTTPS URL.

3. **Clone the Repository**
   - In your terminal, run:
     ```bash
     git clone https://github.com/<your-username>/hello-world.git
     ```
   - Replace the URL with your `hello-world` repository’s URL.

4. **Navigate to the Cloned Directory**
   - Change into the new directory:
     ```bash
     cd hello-world
     ```
   - List the files to confirm:
     ```bash
     ls
     ```
   - You should see `README.md` and other files.

5. **Open the Project in Your Editor**
   - Open the folder in VS Code or your preferred editor for a better experience.

## Best Practices
- **Clone only trusted repositories** to avoid security risks.
- **Keep your local repository up to date** by regularly pulling changes.
- **Use descriptive folder names** if cloning multiple repositories.

## Additional Resources
- [Cloning a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)

[Top](#table-of-contents)

# Step 4: Push Changes

Pushing changes allows you to update the remote repository (on GitHub) with your latest work from your local repository. This is a key part of collaborating and keeping your code backed up.

## Why Push Changes?
- To share your work with others or back it up to GitHub.
- To keep the remote repository up to date with your local changes.
- To collaborate and synchronize with teammates.

## Example Scenario
Suppose you have made changes to your local `README.md` file and want to update the remote repository on GitHub.

### Steps to Push Changes

1. **Make Changes Locally**
   - Open the `hello-world` folder in your file explorer and edit the `README.md` file in a text editor.
   - For example, add the following lines:
     ```markdown
     # hello-world
     A repository for the Software Assurance course at the University of Nebraska at Omaha.
     ```

2. **Check the Status of Your Repository**
   - In your terminal, run:
     ```bash
     git status
     ```
   - You should see which files have been modified.

3. **Stage Your Changes**
   - Add your changes to the staging area:
     ```bash
     git add -A
     ```
   - This command stages all modified, deleted, and new files.

4. **Commit Your Changes**
   - Commit the staged changes with a descriptive message:
     ```bash
     git commit -m "added UNO description"
     ```
   - This creates a checkpoint in your local repository.
   - To run this command you may be prompted to set your username in Git. Learn more about [configuring Git](https://docs.github.com/en/get-started/git-basics/setting-your-username-in-git) for your environment.

5. **Check Your Commit History (Optional)**
   - To see your commits:
     ```bash
     git log
     ```
   - Press `q` to exit the log view.

6. **Push Your Changes to the Remote Repository**
   - Push your local commits to GitHub's default branch (usually `main`):
     ```bash
     git push origin main
     ```
   - For older repositories that still use `master`, replace `main` with your branch name as needed. Use `origin` unless you have renamed your remote.
   - You may be prompted to [authenticate with GitHub](https://docs.github.com/en/get-started/git-basics/set-up-git#authenticating-with-github-from-git) if you haven't already. [Github CLI](https://docs.github.com/en/get-started/git-basics/caching-your-github-credentials-in-git#github-cli) can help you cache your credentials.

7. **Verify the Push**
   - Go to your repository on GitHub.com and confirm that your changes appear.

## Best Practices
- **Write clear commit messages** to describe your changes.
- **Push frequently** to keep your work backed up and in sync.
- **Pull before you push** if you suspect others have made changes to avoid conflicts.
- Use feature branches for new features or experiments, and merge them into the main branch when ready.

## Additional Resources
- [Pushing commits to a remote repository](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository)

[Top](#table-of-contents)

# Step 5: Pull Remote Changes

Keeping your local repository up to date with changes from the remote repository is essential, especially when collaborating with others. This step will show you how to fetch and merge changes made on GitHub.com (or by other collaborators) into your local repository.

## Why Pull Remote Changes?
- To get updates made by others or yourself on GitHub.com.
- To avoid and resolve conflicts before making your own changes.
- To keep your local and remote repositories synchronized.

## Example Scenario
Suppose you or a collaborator edits the `README.md` file directly on GitHub.com (for example, by adding a link to your favorite website).

### Steps to Pull Remote Changes

1. **Edit the File on GitHub.com**
   - Navigate to your hello-world repository on GitHub.com.
   - Edit the `README.md` file (click the file, then the pencil icon).
   - Add a change (e.g., a link), write a commit message, and click "Commit changes".

2. **Check Local Repository Status**
   - In your terminal, run:
     ```bash
     git status
     ```
   - You may see that your local repository is behind the remote repository.

3. **Pull the Latest Changes**
   - Run:
     ```bash
     git pull
     ```
   - This command fetches changes from the remote repository and merges them into your current local branch.

4. **Verify the Update**
   - Check that your local `README.md` file now includes the changes made on GitHub.com.

## Best Practices
- **Always pull before you start working** to minimize merge conflicts.
- If you have local changes, commit or stash them before pulling to avoid conflicts.
- If a merge conflict occurs, Git will prompt you to resolve it before completing the pull.

## Additional Resources
- [Resolving a merge conflict from the command line](https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line/)

[Top](#table-of-contents)

# Step 6: Fork a Repository

Forking a repository allows you to create your own copy of someone else's project. This is a common way to experiment, make changes, and contribute to open source projects without affecting the original codebase.

## Why Fork a Repository?
- To propose changes to someone else's project (via pull requests).
- To use an existing project as a starting point for your own work.
- To experiment safely without affecting the original repository.

## Example Scenario
Suppose you want to contribute improvements to a public project, or you want to customize a project for your own use.

### Steps to Fork and Contribute

1. **Fork the Repository on GitHub**
   - Go to the repository you want to fork (e.g., [https://github.com/robinagandhi/hello-world.git](https://github.com/robinagandhi/hello-world.git)).
   - Click the `Fork` button in the top right corner.
   - This creates a copy of the repository under your own GitHub account.

2. **Make Changes in Your Fork**
   - You can edit files directly on GitHub (e.g., edit `README.md` and add a link or note).
   - Or, clone your fork to your local machine for more extensive changes:
     ```bash
     git clone https://github.com/<your-username>/hello-world.git
     cd hello-world
     ```
   - Make your changes locally, then stage and commit them as usual.

3. **Push Changes to Your Fork**
   - After committing, push your changes to your fork on GitHub:
     ```bash
     git push origin master
     ```
   - Replace `master` with your branch name if different.

4. **Propose Changes to the Original Repository (Pull Request)**
   - On GitHub, go to your forked repository.
   - Click the `Pull requests` tab, then `New pull request`.
   - Compare your changes with the original repository, add a description, and submit the pull request.
   - The owner of the original repository will review your suggestions and may merge them.

## Best Practices
- **Describe your changes clearly** in your pull request.
- **Sync your fork** with the original repository regularly to avoid conflicts.
- Use feature branches for new features or fixes, and submit pull requests from those branches.

## Additional Resources
- [Fork a repo](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
- [About pull requests](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests)

[Top](#table-of-contents)

# Step 7: Markdown

To communicate and write effectively on GitHub, you will need to learn `Markdown`. Markdown is a lightweight markup language that allows you to format text using simple syntax. It is widely used for README files, documentation, and comments on GitHub.

**Why use Markdown?**
- It makes your documentation readable and visually appealing.
- It is easy to learn and quick to write.
- It works directly in GitHub and many other platforms.

**Getting Started:**
1. Explore the basics here: [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
2. Try out Markdown syntax directly on GitHub in any file ending with `.md` (Markdown file). Edit your `README.md` file in your hello-world repository and use the Preview tab to see the formatting. Optionally practice using this interactive tutorial: [markdowntutorial.com](http://www.markdowntutorial.com)
3. **Tip:** Use the built-in Markdown preview in VS Code (`Cmd+Shift+V` on Mac, `Ctrl+Shift+V` on Windows/Linux) to see your formatting live.

**Common Markdown Syntax:**
- `# Heading 1`, `## Heading 2`, ... for headings
- `*italic*` or `_italic_` for italic text
- `**bold**` or `__bold__` for bold text
- Lists: `- item` or `1. item`
- Links: `[text](url)`
- Images: `![alt text](image_url)`
- Code blocks: Use triple backticks (```) before and after your code

**Example:**
```markdown
# My Project

This is a **bold** statement and this is *italic* text.

- Item 1
- Item 2

[Visit UNO](https://www.unomaha.edu)
```

For more advanced formatting, see:
- [Organizing data with tables](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables)
- [Creating and highlighting code blocks](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks)

Learning Markdown will help you communicate more clearly and professionally on GitHub. We will use Markdown extensively in this course for documentation, assignments, and project descriptions.

[Top](#table-of-contents)

# Step 8: Project Management

Effective project management is essential for planning, tracking, and delivering software projects. GitHub provides built-in tools – Issues and Project Boards – to help you organize your work and collaborate with others.

## Issue Tracking

Issues are used to track tasks, bugs, feature requests, and questions. They help you and your team stay organized and ensure nothing falls through the cracks.

**How to create and manage Issues:**
1. Go to the "Issues" tab in your hello-world repository on GitHub.com.
2. Click "New Issue".
3. **Example:** Create an issue titled "Add new updates to README.md" and describe what needs to be added.
4. Assign the issue to yourself or a team member, add labels (e.g., bug, enhancement), and set a milestone if applicable.
5. Click "Submit new issue".
6. Once the issue is resolved, you can close it by clicking the "Close issue" button.
7. You can also comment on issues to discuss details, ask questions, or provide updates.

For more, see: [GitHub Issues Guide](https://guides.github.com/features/issues/)

## Project Boards

Project Boards help you visualize and manage your work using Kanban-style columns (e.g., To Do, In Progress, Done) or a table view. You can also add issues and notes as cards to the board, making it easy to track progress and collaborate with your team.

**How to create and use a Project Board:**
1. Go to the "Projects" tab in your repository.
2. Click "New Project" green button and choose a template (e.g., Team planning or Kanban).
3. Name your project and add columns as needed.
4. Add issues or notes as cards to the board.
5. Move cards between columns to track progress.

You can automate workflows, such as automatically adding new issues to a board or moving cards when issues are closed. See [Project Automation](https://docs.github.com/en/issues/planning-and-tracking-with-projects/automating-your-project/adding-items-automatically).

**Tips:**
- Create project boards to visualize and manage your issues.
- Project boards can be used for personal organization, not just team projects.

For more, see: [GitHub Projects Quickstart](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/quickstart-for-projects)

[Top](#table-of-contents)

# Step 9: AI-Powered Development

Artificial Intelligence (AI) is transforming how software is developed. Tools like **GitHub Copilot** can help you write code faster, learn new concepts, and improve your productivity. It can even assist with documentation and testing.

## What is GitHub Copilot?

GitHub Copilot is an AI pair programmer that offers autocomplete-style suggestions as you code. It can:
- Suggest code completions and entire functions.
- Help write tests and documentation.
- Explain code snippets and suggest improvements.
- Support many programming languages and frameworks.

Copilot is a powerful assistant, but it is **not** a substitute for understanding your code. Understanding is a combination of knowledge, experience, and critical thinking. Copilot can help you learn and improve your coding skills, but it is essential to review and understand its suggestions.
Always review, test, and adapt its suggestions to your needs.

> **Responsible Use:** Do not use Copilot to submit graded assignments that you do not understand or that violates academic integrity policies. You can and should use Copilot to learn and enhance your skills.

## Getting Access as a Student

As a student, you can often get free access to GitHub Copilot through the GitHub Student Developer Pack.

1. Go to the [GitHub Education](https://education.github.com/pack) website.
2. Click "Sign up for Student Developer Pack" and follow the prompts to verify your student status.
3. Once approved, Copilot should be enabled on your GitHub account.

## Installing Copilot in Visual Studio Code

1. Open Visual Studio Code. If you do not have it installed, download and install it from [https://code.visualstudio.com/](https://code.visualstudio.com/).
2. Go to the Extensions view (`Cmd+Shift+X` on Mac or `Ctrl+Shift+X` on Windows).
3. Search for `GitHub Copilot` and install the extension.
4. Sign in with your GitHub account to authorize the extension.

## Using Copilot

- Start typing code or write a comment describing what you want to do. Copilot will suggest code completions.
- To accept a suggestion, press `Tab`.
- You can cycle through alternative suggestions with `Alt` + `[` or `Alt` + `]` on Windows/Linux, or `Option` + `[` or `Option` + `]` on Mac.
- You can also ask Copilot to generate entire functions or classes by writing a comment describing what you want.
- For example, you can write a comment like this in your code editor:

**Example:**
```python
# function to read a csv file and return a list of dictionaries
```
Copilot will suggest the code for this function. Try this in your own `hello-world` repository for practice by creating a new Python file and writing the comment.

## Copilot Chat

Copilot Chat is an interactive tool that lets you ask questions, get code explanations, and brainstorm ideas directly in your editor.

**Example Prompts:**
- "Explain what this function does."
- "Suggest test cases for this function."
- "Refactor this code for readability."
- "Generate a draw.io diagram outline for a login system."

**Tips**
- Write clear comments and descriptive function names to get better suggestions.
- Always review and test Copilot’s output for correctness and security.
- Use Copilot to learn, not to bypass understanding or academic integrity policies.

For more, see the [GitHub Copilot Quickstart](https://docs.github.com/en/copilot/quickstart).

[Top](#table-of-contents)

# Step 10: Automate Your Workflow with GitHub Actions

GitHub Actions is a powerful feature that lets you automate tasks in your software development workflow. With Actions, you can automatically build, test, and deploy your code whenever you push changes to your repository.

**What is CI/CD?**

CI/CD stands for **Continuous Integration** and **Continuous Deployment/Delivery**. These are modern software development practices that help teams deliver code changes more frequently, reliably, and efficiently.

- **Continuous Integration (CI):** Automatically builds and tests your code every time you push changes. This helps catch errors early and ensures that your codebase is always in a working state.
- **Continuous Deployment/Delivery (CD):** Automatically deploys your application to a production or staging environment after passing all tests. This reduces manual work and speeds up the release process.

**What can you do with GitHub Actions?**
- Run tests automatically when you push code (CI).
- Build and deploy your project to production or staging environments (CD).
- Lint code (check for syntax and style issues) and check for formatting issues.
- Automate repetitive tasks like labeling issues or sending notifications.

**How to get started:**
1. Go to the "Actions" tab in your GitHub repository (for example, your `hello-world` repository).
2. We will select `set up a workflow yourself`, but you can choose a workflow template (e.g., Node.js, Python, etc.) if it fits your project.
3. You will be prompted to create a YAML file that defines your workflow. YAML is a human-readable data format used to define workflows in GitHub Actions.
4. Let's start with a simple workflow that runs on every push to your repository.

**Example 1: Lint Markdown Files in Your Hello World Repository (CI)**

Keeping your documentation clean is important! You can use a GitHub Action to automatically check your Markdown files for style issues every time you push changes (an example of CI):

```yaml
name: Lint Markdown

on:
  push:
    paths:
      - '**/*.md'
  pull_request:
    paths:
      - '**/*.md'

jobs:
  markdown-lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Lint Markdown files
        uses: DavidAnson/markdownlint-cli2-action@v15
        with:
          globs: '**/*.md'
```

6. Commit and push your changes to GitHub. Your file will be saved as `.github/workflows/main.yml`.
   - You can also name the file something more descriptive, like `markdown-lint.yml`.
   - The `on` section specifies when the workflow should run (on push or pull request).
   - The `jobs` section defines the steps to run, including checking out the code and running the `markdown-lint` tool.
7. Go to the "Actions" tab in your repository to see your workflow run! You may see several error messages if there are issues with your Markdown files. Review the output to see what needs fixing.

This workflow will run the `markdown-lint` tool on all Markdown files in your repository whenever you push changes or open a pull request. It will check for common formatting issues and report them in the Actions tab.

**Example 2: Run Tests Automatically (CI)**

Suppose you have a Python project with tests. You can use GitHub Actions to automatically run your tests every time you push code:

```yaml
name: Python application

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.x'
      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt
      - name: Run tests
        run: |
          pytest
```

**Example 3: Deploy Automatically (CD)**

You can also set up workflows to deploy your application after tests pass. For example, you might deploy a static website to [GitHub Pages](https://pages.github.com/) or another service. (See GitHub documentation for deployment examples.)

> **CI/CD in Practice:**  
> - CI helps you catch errors early by running tests on every change.
> - CD helps you deliver new features and fixes to users quickly and reliably.

> **Troubleshooting:** If your workflow does not run, check that your YAML file is in `.github/workflows/` and that the syntax is correct (use a YAML linter if needed).

**Learn more:**
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Awesome Actions (community examples), including code scanning](https://github.com/sdras/awesome-actions)
- [What is CI/CD?](https://www.redhat.com/en/topics/devops/what-is-ci-cd)

Automating your workflow with GitHub Actions and adopting CI/CD practices can save time, reduce errors, and help your repository stay organized and up to date.

[Top](#table-of-contents)

# Fork This Course

This course has been developed on GitHub to encourage open collaboration and learning. Now that you are familiar with Git, you can fork this course repository to:

- Customize materials for your own study.
- Experiment with changes and new content.
- Propose improvements or corrections by submitting pull requests.

**How to fork and contribute:**
1. Navigate to the [course repository on GitHub](https://github.com/robinagandhi/swa).
2. Click the "Fork" button to create your own copy of the repository.
3. Make changes in your forked repository—add notes, fix typos, or suggest new content.
4. To share your improvements, submit a pull request back to the original course repository.
5. Your contributions will be reviewed by me, and if accepted, merged into the main course materials.

[Top](#table-of-contents)

# Cybersecurity Reflections

GitHub's collaboration model is designed with cybersecurity principles in mind. Understanding these principles helps you contribute safely and responsibly to open source projects.

- **Least Privilege:** Only the `owner` of a remote repository can push commits directly. Other users must submit pull requests, which the owner reviews and merges if appropriate. Collaborators can push commits but cannot delete the repository or add other collaborators. This enforces the principle of least privilege—users have only the access necessary for their role.
- **Modularization:** Repositories are often designed as self-contained modules. These modules can be integrated into larger projects, making it easier to manage, update, and locate faulty components. Modularization supports collaboration among distributed teams.
- **Domain Separation:** Source code is separated from other resources, allowing for long-term maintenance and versioning. This separation enables teams to manage different product versions and operating environments securely.
- **Secrets Management:** Never commit secrets or passwords to your repository. Use environment variables or GitHub Secrets for sensitive data.
- **Enable Two-Factor Authentication:** For added security, enable two-factor authentication (2FA) on your GitHub account. This helps protect your account from unauthorized access. [Learn more about 2FA](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa).

By following these principles, you help ensure the security, integrity, and maintainability of your code and the projects you contribute to.

[Top](#table-of-contents)

# Additional Resources

**Git and GitHub Basics**
* [Quick start guide](http://rogerdudler.github.io/git-guide/) — A concise, visual introduction to Git.
* [GitHub cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf) — Handy reference for common Git commands.
* [Official Git Documentation](https://git-scm.com/doc) — Comprehensive documentation for Git.
* [GitHub Learning Lab](https://github.com/apps/github-learning-lab) — Interactive GitHub tutorials.

**GitHub Features and Best Practices**
* [GitHub tutorials collection](https://help.github.com/articles/git-and-github-learning-resources/) — Curated list of GitHub learning resources.
* [How To: Ignore files during a check into GitHub](https://help.github.com/articles/ignoring-files/) — Guide to using .gitignore.
* [Socialize on GitHub](https://guides.github.com/activities/socialize/) — Tips for collaborating and networking.
* [Documenting your Project on GitHub](https://guides.github.com/features/wikis/) — Using wikis for project documentation.
* [Creating webpages on GitHub](https://guides.github.com/features/pages/) — Introduction to GitHub Pages for hosting websites.

**AI and Automation**
* [GitHub Copilot: Quickstart](https://docs.github.com/en/copilot/quickstart) — Get started with Copilot, GitHub’s AI coding assistant.
* [GitHub Actions Documentation](https://docs.github.com/en/actions) — Automate workflows with GitHub Actions.

[Top](#table-of-contents)

# Acknowledgements

* A special thanks to Matt Hale, Aaron Vigal and Cade Wollcot for reviews on early drafts of this module and thoughtful discussions.

[Top](#table-of-contents)

# License

This work is licensed under a Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.
