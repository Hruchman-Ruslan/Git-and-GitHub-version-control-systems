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
