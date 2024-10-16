# Introduction
## What is git...?
Git is ==a free, open-source version control system (VCS) that helps track changes to code files and projects==. It's the most widely used **VCS** in the world and is considered the modern standard for software development.
## Types of version control
### Centralised
- In a centralised version control system, there is a single central server that contains all the versioned files. Eg:SVN,CVS
- CVCS relies on a central server, is simpler but less robust if the server falls
### Distributed
- In a distributed version control system, every user has a complete copy of the entire repository. EG: Git, Mercurial
- DVCS distributes the full repository to every user, providing more flexibility and robustness at the cost of complexity.
![](https://www.techforceservices.com/wp-content/uploads/2019/05/Types-of-Version-Control-760x300-1.png)
## difference between git and GitHub...?
The key difference **between** Git and GitHub is that Git is a free, open source version control tool that developers install locally on their personal computers, while GitHub is a pay-for-use online service built to run Git in the cloud. Git is a piece of software. GitHub is an online SaaS service.

|                    | GIT                                                     | GITHUB                                                                     |
| ------------------ | ------------------------------------------------------- | -------------------------------------------------------------------------- |
| purpose            | Version control tool used for tracking changes in code. | Hosting service for git repositories with collaboration features.          |
| Scope              | Local tool user by developers on their machines.        | Online platform that integrates with git and provides additional services. |
| Accessibillity     | Requires command line usage; primarily a back-end tool  | user friendly web interface with additional features for collaboration     |
| Offline capability | Fully functional offline.                               | Requires internet access to use its online features.                       |
## What is version control system...?
The management of changes to documents, computer programs, large web sites, and other collections of information.
- **Directory** -> Folder
- **Terminal or Command Line** -> Interface for text commands
- **CLI** -> Command Line Interface
- **CD** -> Change Directory
- **Code Editor** -> Word processor for writing code
- **Repository**, **repo** -> Project, or the folder/place where your project is kept.
- **Git Hub** => A website to host your repositories online.
## Git Commands
- **clone** => Bring a repository that is hosted somewhere like GitHub into a fore on your local machine
- **add** => Track your files and changes in Git
- **commit** => Save your files in git. A snapshot of your project's files at a specific point in time, like a save point in a game.
- **push** => Upload git commits to a remote repository, like GitHub
- **pull** => Download changes form remote repository to your local machine, the opposite of  push
- **branch** => a parallel version of your main project where you can work on different features or fixes
- **remote** => A version o your repository hosted on the internet or network (eg. GitHub)
- **Merge** => Combining changes from one branch into another, usually integration new feature or fixes.
- **pull request** => A request to merge changes form one branch into another, often reviewed before approval.
- **fetch** => Downloading changes from a remote repository without merging them into your local branch.
- **fork** => Creating your own copy of someone else's repository to make changes without affecting the original.
- **stash** => Temporarily saving changes that aren't ready to be committed, so you can work on something else.
- **conflict** => occurs when different changes in two branches can't be automatically merge and need manual resolution
- **head** => the current commit your repository is on typically the lats commit in the current branch.
- **origin** => the default name for a remote repository from which you cloned your project.
- **rebase** => moving or combining a sequence of commits to a new base commit, often used to keep a linear project history.
- **gitignore** => a file specifying which files or dir to ignore in a repository, often used for project management or GitHub.
- **issue** => A way to track bugs, enhancements, or other tasks in a repository, often used for project management of GitHub.
![[Pasted image 20241006095905.png]]
### working directory
A working directory is **a folder you create to store all your project's files**. A Git directory is a folder Git creates in the working directory you instructed it to monitor.
### staging area
The staging area is **a file, generally contained in your Git directory, that stores information about what will go into your next commit**. Its technical name in Git parlance is the “index”, but the phrase “staging area” works just as well.
### local repo
A local repository is **a copy of the entire project's history and code base that resides on a developer's machine**. When a developer initialises a local repository, Git sets up the necessary infrastructure to track changes, branches, and commits within the project.
![[Pasted image 20241006104759.png]]

# Git command
## Configure

| Name  | Command                                            | Explanation                                                  |
| ----- | -------------------------------------------------- | ------------------------------------------------------------ |
| Name  | `git config --global user.name "[name]"`           | Sets the name you want attached to your commit transactions. |
| Email | `git config --global user.email "[email address]"` | Sets the email you want attached to your commit transactions |
| color | `git config --global color.ui auto`                | Enables helpful colourisation of command line output         |
| Alias | `git config --global alias.co 'check out'`         | Create shortcuts for git commands to save time               |
### 1. Local Git Config:

This is the default level for git config. The local level of Git config is specific to a particular repository. It allows you to set configurations that are relevant only to that repository. This level takes precedence over global and system configurations. Local configurations are stored in the `_.git/config_` file within the repository.

Example: To set the user name for a specific repository, use the following command:  
```  
**_git config user.name “Your Name”_**  
```  
This command sets the user name to “Your Name” only for that repository.

### 2. Global Git Config:

The global level of Git config applies settings to the currently logged-in user across all repositories. It enables you to maintain consistent configurations for your personal preferences. Global configurations are stored in the `_~/.gitconfig_` file in your home directory.

Example: To set the user name globally, use the following command:  
```  
**_git config — global user.name “Your Name”_**  
```  
This command associates the name “Your Name” with your user account, which will be used as the author information for commits made across different repositories.

### 3. System Git Config:

The system level of Git config controls settings for all users and repositories on your computer. It applies globally and affects all repositories, regardless of the logged-in user. System configurations are stored in the `_/etc/gitconfig_` file and usually require administrative privileges to modify.

Example: To set the user name at the system level, use the following command:  
```  
**_git config — system user.name “Your Name”_**  
```  
This command sets the user name to “Your Name” for all users and repositories on the system.

Managing Configurations:

To remove or unset a configuration option, you can use the ` _— unset_` flag with the appropriate level. For example, to remove the global user name configuration, you would run:  
```  
**_git config — global — unset user.name  
_**
```  
Similarly, you can unset other configuration options like user email, or any other configuration option.

## Create repositories

| Name   | command                       | explanation                                                                                                |
| ------ | ----------------------------- | ---------------------------------------------------------------------------------------------------------- |
| init   | `git init`                    | Turns an existing directory into a new Git<br>repository inside the folder you are<br>running this command |
| origin | `git remote add origin [url]` | Specifies the remote repository for<br>your local repository                                               |
| clone  | `git clone [url]`             | Clone (download) a repository that<br>already exists on GitHub                                             |
## Make changes
| name     | command                                     | explanation                                                                                |
| -------- | ------------------------------------------- | ------------------------------------------------------------------------------------------ |
| log      | `git log`                                   | Lists version history for the<br>current branch                                            |
| log file | `git log --follow [file]`                   | Lists version history for a file,<br>beyond renames                                        |
| show     | `git show [commit]`                         | Outputs metadata and content<br>changes of the specified commit                            |
| diff     | `git diff [first-branch]...[second-branch0` | Shows content differences<br>between two branches                                          |
| status   | `git status`                                | Provides an overview of the current state of the working directory and the staging<br>area |
| add      | `git add [file]`                            | Snapshots the file in preparation<br>for versioning                                        |
| commit   | `git commit -m "[your message]"`            | Records file snapshots<br>permanently in version history                                   |
## Redo commits
| Name       | command                     | explanation                                                      |
| ---------- | --------------------------- | ---------------------------------------------------------------- |
| reset      | `git reset [commit]`        | Undoes all commits after [commit],<br>preserving changes locally |
| reset hard | `git reset --hard [commit]` | Discards all history and changes back<br>to the specified commit |
## Branches
| Name          | Command                       | Explanation                                                           |
| ------------- | ----------------------------- | --------------------------------------------------------------------- |
| new branch    | `git branch [branch-name]`    | Create a new branch                                                   |
| switch        | `git switch -c [branch-name]` | Switches to the specified branch<br>and updates the working directory |
| merge         | `git merge [branch]`          | Combines the specified branch's<br>history into the current branch    |
| delete branch | `git branch -d [branch-name]` | Deletes the specified branch                                          |
## synchronise changes
| Name  | Command     | Explanation                                                    |
| ----- | ----------- | -------------------------------------------------------------- |
| fetch | `git fetch` | Downloads all history from the<br>remote tracking branches     |
| merge | `git merge` | Combines remote tracking<br>branches into current local branch |
| push  | `git push`  | Uploads all local branch commits<br>to GitHub                  |
| pull  | `git pull`  | git pull is a combination of git<br>fetch and git merge        |
# Branching & Merging
## Branch
A parallel version of your main project where you can work on different features or fixes.
## Merge
Combining changes from one branch into another, usually integrating new features or fixes
![](https://miro.medium.com/v2/resize:fit:625/1*9YsM1sNaQQut7-GDcuHKBg.png)

## Merge conflict
- Merge conflict arise when two files having same content modified, are merged.
- It can occur on merging branches or when merging forked history together.
	[merge conflict full explanation](https://phoenixnap.com/kb/how-to-resolve-merge-conflicts-in-git#ftoc-heading-1)
	[merge conflict => Atlassian](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)
### Resolve merge conflict
- Merge conflict are resolved manually by users
- git provides different merge-tools to compare and choose the required changes
- User can also use third party merge-tools with git
## Stashing
- Stashing in git is a way to temporarily save changes you've made in your working directory without committing them.
- This is useful if you need to switch branches or work on something else without losing your current changes.

| Name    | command                              | Explanation                                                   |
| ------- | ------------------------------------ | ------------------------------------------------------------- |
| stash   | `git stash`                          | This saves your changes and<br>cleans your working directory. |
| message | `git stash save "your message here"` | This saves your changes with a<br>descriptive message.        |
| clear   | `git stash clear`                    | This removes all stashes from the<br>list.                    |
| apply   | `git stash apply`                    | This reapplies the most recent<br>stashed changes.            |

## Git Rebase
- Rebase is a way of combining the work between different branches.
- It  is used to make Linear sequence of commits
- The commit log or history if repository  stays clean if re-basing is done

| Name                                      | command                                       | explanation                                                                                                                 |
| ----------------------------------------- | --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Rebase current branch onto another        | `git chekout feature-branch``git rebase main` | This will move the commits from<br>feature-branch onto the tip of main                                                      |
| Interactive rebase                        | `git rebase -i HEAD -3`                       | This starts an interactive rebase for<br>the last 3 commits. It allows you to<br>edit, reorder, squash, or drop<br>commits. |
| continue rebase after conflict resolution | `git rebase --continue`                       | After resolving conflicts during a<br>rebase, use this command to<br>continue the process.                                  |
| skip commit during rebase                 | `git rebase --skip`                           | If a connit causes conflicts that you want to skip, use this to skip applying that commit                                   |
| abort rebase                              | `git rebase --abort`                          | This stops the rebase process and returns the branch to its original state before the rebase began.                         |

## Merge vs rebase
### Rebase
Moving or combining a sequence of commits to a new base commit. This rewrites the commit history of the rebased branch.
**When we use rebase**
- *Local Changes* => When you're working on local changes that haven't
been shared with others.
- *Clean History* => When you want a clean, linear history, especially before merging a feature branch into the main branch.
### Merge
Combining the changes from one branch into another by creating a new commit, known as a merge commit. This keeps the commit history of both branches intact.
**When we use merge**
- When working with a team on shared branches, use merge to ensure everyone's history remains consistent.
- When you want to preserve the full history of branch merges for record-keeping and debugging.
# GitHub
- GitHub is a web-based platform for version control and
collaboration, built around Git.
- It enables multiple people to work on projects together from
anywhere, providing tools for project management, issue tracking,
code review, and more.

| Repository (Repo)                                                                              | Fork                                                                                                                        |
| ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| - A storage space for your project's code including files and the complete history of changes. | - A personal copy of someone else's repository. It allows you to freely make changes without affecting the original project |
| Example: github.com/username/repo-name                                                         | Example: Forking github.com/original-user/repo-name to github.com/your-user/repo-name                                       |

| Clone                                                                                                                                                   | Pull request                                                                                                                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| • A local copy of a repository that you can<br>work on from your own computer.<br>• Example: git clone<br>https://github.com/username/repo-<br>name.git | - A method of submitting contributions to a project. When you open a pull request, you're asking the original repository to pull your<br>changes into their codebase.<br>- Example: Opening a pull request from feature-<br>branch in your fork to main in the original<br>repository. |

# GitHub [[GitHub]]
