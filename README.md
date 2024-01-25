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
