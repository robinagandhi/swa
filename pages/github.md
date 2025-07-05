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
To create a `Local` repository, git has two basic options.
1. `Clone` a remote repository on your computer, or
2. `Initialize` a new git repository from scratch on your computer.

[Top](#table-of-contents)

## Clone a remote repository
Let's start by looking at option #1. First, check if Git is installed.

- Git tools are not pre-installed on all operating systems.
- To check if they exist on your operating system, open up a command line interface (`PowerShell` for Windows, `Terminal` for Mac OS or Linux) and type:

```bash
git --version
```

- If Git is installed, this command will show the version installed. If the command is not recognized, then it means you need to install git on your OS. The information available at [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) can walk you through it for a variety of OSes.
- Just for demonstration, I will assume a Windows OS environment with Powershell (similar to a Terminal on Mac OS or Linux) as shown below:

You should see output similar to the following, indicating the installed version:

```
git version 2.39.5 (Apple Git-154)
```

To `clone` a remote repository (what we set out to do), we first need a ```reference URL``` to find it.   
* On `GitHub.com`, navigate to your hello-world repository and click on the green button that says ```<> Code```.   
* Copy the URL under Clone that starts with HTTPS.  
* Now we are ready to clone this remote repository, and create a local repository.

```bash
git clone <<replace this, including the angled brackets, with the copied URL>>

```

For example, my hello-world repository URL is `https://github.com/robinagandhi/hello-world.git` so the command to clone it will be:

```bash
git clone https://github.com/robinagandhi/hello-world.git

```

Once you issue this command, you will start to see some download messages, and upon success, your local repository will be ready for use. You may be asked to authenticate with GitHub credentials if your repository is not public.

```
Cloning into 'hello-world'...
remote: Enumerating objects: 85, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 85 (delta 0), reused 1 (delta 0), pack-reused 82 (from 1)
Receiving objects: 100% (85/85), 25.98 KiB | 5.19 MiB/s, done.
Resolving deltas: 100% (22/22), done.

```

Now, in PowerShell, switch to the hello-world directory that has all the files from the repository that you just cloned.

> **Tip:** Open the `hello-world` folder in VS Code or your preferred editor for a more hands-on experience.

```bash
cd hello-world/
```

To list the files in this directory, use this command.

```bash
ls
```
You should see a README.md and possibly some other files.

## Initialize a new repository

> **NOTE:** We do not need to use this option currently, so you may move to [Step 4](#step-4)

If you need to create a new repository you will navigate to the folder (using the `cd` command) containing the files you wish to version control and then use the init command:
```bash
# Create a new directory
mkdir test
# Switch to that directory
cd test
# Initialize a new git repository
git init
```

That's it! This option is useful if you are **creating new files from scratch**. Using GitHub, you can also push newly tracked files such as these to a remote repository. The steps are the same as you will see for cloned repositories below.

[Top](#table-of-contents)

# Step 4: Push Changes
In this step, we will make changes to the files in our `Local` repository and then `push` changes back to the `remote` repository.

Git is based on a **de-centralized** model of ownership - which means that there is no central authoritative repository. Every repository, Local or Remote, is fully autonomous and fully functional on its own. So changes made in any repository are tracked in that repository only. Two repositories do not communicate unless there is an explicit request to synchronize changes across them. This constraint will make more sense as we work through a scenario.

Let's open the hello-world folder in your file explorer and make changes to the `README.md` file in a text editor.  

For example, you could add the following lines to your `README.md` file:

```markdown
# hello-world
A repository for the Software Assurance course at the University of Nebraska at Omaha.
```

Once you save the edited README.md, check the status of the local repository using the following command. Return to Powershell:

```bash
git status
```
You should see something like this:

```
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

A few things to notice here about these status messages:  
1. `On branch master`: You are on the master branch in your `local` repository. More recently, many git tools use the name `main` instead of `master` for more inclusive terminology. 
2. `Your branch is up-to-date with 'origin/master'`: Your local repository master branch is in sync with your remote repository master branch on GitHub. The default name for the remote repository is **origin**. This name makes sense as you cloned your local repository from it.  
3. `Changes not staged for commit`: git follows a two-step process to save changes to a repository.
  1. The user indicates which modified/deleted/new files need to be `staged` for a save in the repository.
  2. The staged files are `committed` to the repository.   
    We will see both these steps in action below.
4. `modified:  README.md`: git knows that you modified README.md file.

Now we `stage` our changes for a commit using this command:
```bash
git add -A
```
The above command `adds` any edited files (including deleted files) in the entire working tree in a staging area called the `index`, which is a temporary holding place before a commit. Instead of `-A`, with this command you may specify a file name or directory from which to update the staging area. Now, recheck the status of the repository using the following command:

```bash
git status
```
You should see something like this:

```
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   README.md
```

This time the modified files are `staged` and appear in green. These changes are ready to be committed.

Before we `commit` these files into our local repository, the author details need to be set. This constraint is for accountability of commits. Using the commands below, save your information to the git configuration files and set them for all of your local repositories. Make sure to use the **same name and email** you used to register with GitHub.

```bash
git config --global user.name "replace this with your name"
git config --global user.email youremail@example.com
```

The `--global` flag indicates that these settings will apply to all repositories on your computer. If you want to set these parameters for a specific repository only, you can run the same commands without the `--global` flag while in that repository directory.

Check your configuration changes by using the following command:
```bash
git config --list
```
You should see your name and email in the output. 

Now let's commit the changes that we staged before. Here we use the `commit` option with `-m` to provide a short commit message. The message helps us semantically annotate various checkpoints in our editing process. These messages are beneficial when rolling back changes to an earlier commit.

```bash
git commit -m "added UNO description"
```

Use this command to see all your commits:

```bash
git log
```

This command shows a summary of commits in the repository, starting with the most recent. Observe the hash code, user details and commit message. These attributes provide attribution of all changes in the code repository, promoting code integrity.

> Hit the key `q` to exit the log of commit messages.

To see a specific commit use the following command with a commit-id, such as: `585db21052a558e7ca917db7d04e684c229e37e3` or just the first 7 digits `585db21`.

```bash
# replace commit-id in the command below
# You can find them using the git log command
git show commit-id
```

> Hit the key `q` to exit

Issue this command to check your repository status once again:
```bash
git status
```

It should report **no** uncommitted changes. But it indicates that `Your branch is ahead of 'origin/master' by 1 commit`. It means that the local repository master branch has more recent commits than the **remote** repository master branch.

To push our local commits to the remote repository (GitHub in this case), we need the git `push` command. However, this command will not work until we authenticate with GitHub. I recommend that you use `GitHub CLI` to authenticate with GitHub. It is a command line tool that allows you to interact with GitHub from the terminal. You could also use Github Desktop or other GUI tools, but the CLI is more versatile and powerful.

- Install [GitHub CLI](https://github.com/cli/cli#installation) on macOS, Windows, or Linux.
- Once installed, open the command line and enter `gh auth login`, then follow the prompts.
- When prompted for your preferred protocol for Git operations, select HTTPS.
- When asked if you would like to authenticate to Git with your GitHub credentials, enter `Y`.

After a successful authentication, to issue the `push` command, we need to indicate the name of the remote repository followed by the name of the local repository branch that has updates to be pushed. Do you remember the name of our remote repository and the main branch?

> **Questions**  
> - What is the default name of the remote repository?  
> - What is the name of the main branch in a repository?

To `push` local commits in the current branch to a remote repository (`origin` in our case) and its remote branch (`master` or sometimes `main`), use the following command:

```bash
 git push origin master
```

> While pushing changes from a local branch, you may rename the branch in the remote repository, you would add one more argument to the push command.  
> `git push  <REMOTENAME> <LOCALBRANCHNAME>:<REMOTEBRANCHNAME>`  
> This command pushes the LOCALBRANCHNAME to your REMOTENAME but renames it as REMOTEBRANCHNAME.  
> This option would be useful if you made local commits on the master branch but want to push your changes to a feature branch on origin.
> If you are using a different branch name, replace `master` with your branch name in the above command.
> If you are using a different remote repository name, replace `origin` with your remote repository name in the above command.

Now, issue the `status` command to check your repository status once again:

```bash
git status
```
You should see a message indicating that your branch is up to date with 'origin/master' and no changes to be committed. This means that your local repository is now synchronized with the remote repository on GitHub. If you navigate to your repository on GitHub.com, you will see your commit message and the changes reflected in the `README.md` file.

As mentioned before in the introduction, git version control is very efficient for text files. It does not store entire files for old versions but only the differences. **So it is prudent to make frequent commits** and then push these changes to the remote repository - so that you have as many checkpoints as possible should you need to roll back. 

To keep the master branch commits clean, you should do feature development and testing in a feature branch and then merge with master.

[Top](#table-of-contents)

# Step 5: Pull Remote Changes
What happens if we make some changes to README.md on `GitHub.com`? Or another collaborator makes changes to it. How do we get these changes back into our local repository? We will learn just that in this step.

Navigate to your hello-world repository on `GitHub.com` and edit the `README.md` file. You can do this by clicking on the file name in the repository view, then clicking the pencil icon to edit it. 

Add a link to your favorite website, for example, [https://www.unomaha.edu](https://www.unomaha.edu) and save the changes.

After making your changes, add a commit message and click the `Commit changes` button.

Your `README.md` file will now be updated with the new link.

Now the remote repository is one `commit` ahead of the local repository. You can verify this by going back to your local repository in a terminal and using the `git status` command. 

To bring the _local_ repository up to speed, we use the following command in a terminal.

```bash
git pull
```
The `git pull` command fetches remote changes (`git fetch`) and merges them (`git merge`) into the current local branch.

After pulling the changes, your local `README.md` file will be updated with the new link.

At this point, you know enough to keep both the local and remote repositories synchronized.    

As long as you always `pull` before making changes and keep `pushing` any new changes - you will avoid most merge conflicts that can occur.  

By default, git attempts to auto-merge changes. But in a collaborative project, conflicts will happen. In that case, git will provide guidance regarding the conflicts and where you will need to make changes before attempting a merge.

If you are interested in learning more about complex team interaction scenarios - you may want to explore a concept called `branching`; for more information about merge conflicts see: [https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line/](https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line/).

[Top](#table-of-contents)

# Step 6: Fork a Repository

Now we will learn about **forking** a repository.

A fork is a copy of a repository. Forking allows you to experiment with changes without affecting the original project. You can use forks to propose changes to someone else's project (via pull requests) or to use their project as a starting point for your own ideas.

**How to Fork and Contribute:**

1. Go to my hello-world repository [https://github.com/robinagandhi/hello-world.git](https://github.com/robinagandhi/hello-world.git).
2. Click the `Fork` button in the top right corner, just above the green `<> Code` button.
3. This creates a copy of my repository under your own GitHub account. You can verify this by checking your repositories list on your GitHub profile.
4. In your forked repository, you can make changes directly on GitHub. For example, edit the `README.md` file by clicking it, then clicking the pencil icon to edit. Add a link to your favorite website (e.g., [https://www.unomaha.edu](https://www.unomaha.edu)), then save your changes with a commit message.
5. **Clone your fork locally** to make more extensive changes. To do this, use the `git clone` command with your fork's URL.
6. Make changes locally, commit, and push to your fork on GitHub.
7. To propose your changes to my hello-world repository, click the `Pull requests` tab in your forked repository, then click `New pull request`. This will compare your changes with my repository. Add a description explaining your changes and submit the pull request.

As the owner of my hello-world repository, I will be notified of your pull request. Now I can review your suggestions, request additional changes, or merge your contribution as is. If merged, your changes become part of my hello-world repository.

To summarize this step, **forking and pull requests** are essential for open source collaboration. They allow you to experiment safely, propose improvements, and contribute to projects you do not own.

And that is one way you can collaborate using GitHub. 

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

**What can you do with GitHub Actions?**
- Run tests automatically when you push code to your repository on GitHub.
- Build and deploy your project to production or staging environments.
- Lint code (check for syntax and style issues) and check for formatting issues.
- Automate repetitive tasks like labeling issues or sending notifications.

**How to get started:**
1. Go to the "Actions" tab in your GitHub repository (for example, your `hello-world` repository).
2. We will select `set up a workflow yourself`, but you can choose a workflow template (e.g., Node.js, Python, etc.) if it fits your project.
4. You will be prompted to create a YAML file that defines your workflow. YAML is a human-readable data format used to define workflows in GitHub Actions.
5. Let's start with a simple workflow that runs on every push to your repository.

**Example 1: Lint Markdown Files in Your Hello World Repository**

Keeping your documentation clean is important! You can use a GitHub Action to automatically check your Markdown files for style issues every time you push changes:

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

> **Troubleshooting:** If your workflow does not run, check that your YAML file is in `.github/workflows/` and that the syntax is correct (use a YAML linter if needed).

**Learn more:**
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Awesome Actions (community examples), including code scanning](https://github.com/sdras/awesome-actions)

Automating your workflow with GitHub Actions can save time, reduce errors, and help your repository stay organized.

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
- **Security Tip:** Never commit secrets or passwords to your repository. Use environment variables or GitHub Secrets for sensitive data.
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