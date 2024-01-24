# Git and GitHub Version Control Systems

This project was created to facilitate learning the Git version control system and GitHub. Below, you will find useful commands along with their descriptions that you can use in the terminal.

## Global Git Settings

- `git config --list`<br>List all configuration settings for the current Git repository;
- `git help config` or `git config --help`<br>Display help information for the "config" command;

## SSH Key Settings

- `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`<br>Generate a new RSA SSH key pair;
- `eval "$(ssh-agent -s)"`<br>Start the SSH agent and print necessary environment variables;
- `ssh-add ~/.ssh/id_rsa`<br>Add RSA private key to the SSH agent for authentication (Windows);
- `ssh-add --apple-use-keychain ~/.ssh/id_rsa`<br>Add RSA private key to the SSH agent for authentication (macOS);
- `cat ~/.ssh/id_rsa.pub`<br>Display the content of the RSA public key file;

## GitHub SSH Key Configuration

### Copy the content of the public key and paste it into GitHub settings

#### Visit: [GitHub SSH Key Settings](https://github.com/settings/keys)

##### Click on "New SSH key," insert the key, give it a name, and click "Add SSH key"

## Cloning a Repository

- `git clone <repo-url>`<br>Clone a repository from the specified URL;
- `git clone <repo-url> <local-name>`<br>Clone a repository from the specified URL and name the local directory;

## Opening the Project in VSCode

- `code .`<br>Open the Visual Studio Code editor in the current directory;
- `code ~/path/to/your/directory`<br>Open the Visual Studio Code editor in the specified directory;
