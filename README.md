# Git and GitHub Version Control Systems

This project was created to facilitate learning the Git version control system and GitHub. Below, you will find useful commands along with their descriptions that you can use in the terminal.

## Global Git Settings

- `git config --list` - List all configuration settings for the current Git repository;
- `git help config` or `git config --help` - Display help information for the "config" command;

## SSH Key Settings

- `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` - Generate a new RSA SSH key pair;
- `eval "$(ssh-agent -s)"` - Start the SSH agent and print necessary environment variables;
- `ssh-add ~/.ssh/id_rsa` - Add RSA private key to the SSH agent for authentication (Windows);
- `ssh-add --apple-use-keychain ~/.ssh/id_rsa` - Add RSA private key to the SSH agent for authentication (macOS);
- `cat ~/.ssh/id_rsa.pub` - Display the content of the RSA public key file;

## GitHub SSH Key Configuration

### Copy the content of the public key and paste it into GitHub settings

### Visit: [GitHub SSH Key Settings](https://github.com/settings/keys)

### Click on "New SSH key," insert the key, give it a name, and click "Add SSH key"

## Cloning a Repository

- `git clone <repo-url>` - Clone a repository from the specified URL;
- `git clone <repo-url> <local-name>` - Clone a repository from the specified URL and name the local directory;

## Opening the Project in VSCode

- `code .` - Open the Visual Studio Code editor in the current directory;
- `code ~/path/to/your/directory` - Open the Visual Studio Code editor in the specified directory;

## Creating a local repository

- `git init` - Initializes a new Git repository in the current directory (
  To view the initialized project's folder, ensure hidden folders are visible.);

## Linking a local repository to a remote one on GitHub

- `git remote add origin <SSH-URL>` - git@github.com:username/repository.git (with SSH key configured) or <https://github.com/username/repository.git> (no SSH key configured);
- `git remote -v` - Check to which remote repository your local one is bound;
- `git remote set-url origin <SSH-URL>` - Updates the URL of the remote repository;

## Local repository status

- `git status` - Checking the status of the repository;

## Adding to version control

- `git add <someFile.txt>` - Adds the file "someFile.txt" to the staging area in Git, preparing it for the next commit;
- `git add *.txt` - Adds all files with the ".txt" extension in the current directory to the staging area in Git, preparing them for the next commit;
- `git add .` - Stages all changes for the next commit;
- `git add drafts` - Stages the "drafts" directory for the next commit, including any changes within it;
- `git add -A` - Stages all changes (new, modified, and deleted files) in the entire working directory for the next commit;
- `git add --all` - The same thing git add -A;

## Cleaning from version control

- `git rm --cached <file>` - Unstages a file, keeping it in the working directory;
- `git reset <your.txt>` - This command will remove your.txt from the index, but preserve any changes you made to the file;
- `git reset` - Unstages changes, keeping them in the working directory;
- `git reset --hard` - Resets the index and working directory to the state of the last commit, discarding all unsaved changes. This can be a risky operation as it may result in the loss of modifications, so use this command with caution;

## .gitignore file

- `*.txt` - Ignore all .txt files;
- `config.json` - Ignore a specific file;
- `drafts/*` - Ignore all files in a specific directory;
- `*.txt !plans.txt` - Ignore all .txt files except plans.txt;

## Recording of changes in the project

- `git commit -m "add a new task"` - Records changes to the repository with a message describing the update;
- `git commit --amend -m "update your message` - Is used to modify the last commit, allowing you to add changes or edit the commit message;
- `git log` - Is a command to view the history of commits in a Git repository;
- `git log -n <quantity>` - Will show the specified number of recent commits;
- `git log --since=<times_period>` - Will show the commits created during the given time;
- `git log --author="author name"` - Will show commits made by a specific author;

## Working with the stack of changes (Stashing)

- `git stash` - This command stores your pending changes (both tracked and untracked files) in a special temporary location called "stash;
- `git stash save "my-comment"` - This command does the same but under the name you specify so that there is no confusion later;
- `git stash list` - Command to view the Stash list;
- `git stash pop` - A command to apply the most recent pending changes and remove them from the stack;
- `git stash apply stash@{<number_stash>}` - Apply a particular stash without removing it from the stack;
- `git stash drop stash@{<number_stash>}` - Remove a specific stash from the list;
- `git stash clear` - To delete all saved change stacks;

### To apply pending changes from the cache, your current code must be committed, otherwise you will receive an application error.

## Pushing changes to GitHub

- `git push` - The command pushes your local commits to the remote repository;
- `git branch -M main` - Renames the default branch master to main;
- `git push -u origin main` - Sends committed changes to the remote repository to the remote main branch;

If you are working with the local version of the newly created remote repository, that is, its remote version is still empty and without any branch, then the git push command will not work. Therefore, first you need to create and rename the main branch.

## Working with branches in Git

- `git branch` - Shows only local branches;
- `git branch -r` - Shows only remote branches;
- `git branch -a` - Shows all branches, both local and remote;

## Creating a new branch

- `git switch -c <your name branch>` - Creates and switches to a branch;
- `git checkout -b <your name branch>` - Creates and switches to a branch;

git switch -c is a modern, concise command for creating and switching to a new branch, while git checkout -b is an older alternative with the same functionality.

- `git switch <your name branch>` - Switch to another branch (new command);
- `git checkout <your name branch>` - Switch to another branch (old command);

## Working with remote branches

- `git fetch` - Downloads the latest changes from the remote repository, but does not commit them to the current branches;
- `git pull` - Simultaneously downloads and commits all recent changes (on all branches) to the local repository;
- `git pull origin <your branch>` - This command will download and apply all changes from the remote <your branch> to the local one;

## Merge branches

- `git merge <your branch>` - This command will try to merge the <your branch> into your current branch;
- `git push origin <your branch>` - This command will start changes to the remote <your branch>;

Еhe merge will be performed exactly in the branch where you are, so don't forget to update it to the latest changes

### Merge branches example:

- `git switch main` - Transition to the main branch;
- `git pull origin main` - Download the latest changes to this branch;
- `git merge <your branch>` - While in the main branch, we merge from <your branch> into the main branch;
- `git push origin main` - We send changes to the remote repository;

!!! This is as an example, but take into account that when working with a team, you can never push to the main branch !!!

## Removing branches

- `git branch -d <your branch>` - Will delete <your branch> ps: -d means "delete". If the branch was merged, it will be removed without problems;
- `git branch -D <your branch>` - Will delete <your branch> ps: -D is force delete. If the branch was not merged and you still want to remove it;
- `git push origin --delete <your branch>` - Will delete the remote <your branch>;

## Local resolution of conflicts

When you run code and get a conflict, Git marks the conflicting areas like this:

<<<<<<< HEAD // start of conflicting lines, current branch is marked as HEAD

<p>Branch header</p> // code from the current header branch that causes the conflict
======= // separator between branch code
<p>Branch footer</p> // code from the footer branch that causes the conflict

> > > > > > > footer // end of conflict, the name of the branch you are trying to merge with

Resolving conflicts: You need to choose which version to keep, or combine changes from both versions. Edit the files to resolve conflicts by removing Git tags and selecting the content you want. This can be done manually or by clicking on the appropriate options.

But this is how you can resolve the conflict with the help of built-in options, where you can accept current changes, incoming changes or accept both options.

![Result of Conflict](https://i.postimg.cc/j50XKmHQ/conflict.jpg)

After resolving all conflicts, use the git add command to add the changed files. You hereby confirm that the conflicts have been resolved.
Complete the merge process using the git commit command. Git will create a new change commit with a merge notification
