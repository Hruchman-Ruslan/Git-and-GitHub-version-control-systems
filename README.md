<h1 align="center"># Git and GitHub Version Control Systems</h1>

This project was created to facilitate learning the Git version control system and GitHub. Below, you will find useful commands along with their descriptions that you can use in the terminal.

<h2 align="center">## Global Git Settings</h2>

- `git config --list` - List all configuration settings for the current Git repository;
- `git help config` or `git config --help` - Display help information for the "config" command;

<h2 align="center">## SSH Key Settings</h2>

- `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` - Generate a new RSA SSH key pair;
- `eval "$(ssh-agent -s)"` - Start the SSH agent and print necessary environment variables;
- `ssh-add ~/.ssh/id_rsa` - Add RSA private key to the SSH agent for authentication (Windows);
- `ssh-add --apple-use-keychain ~/.ssh/id_rsa` - Add RSA private key to the SSH agent for authentication (macOS);
- `cat ~/.ssh/id_rsa.pub` - Display the content of the RSA public key file;

<h2 align="center">## GitHub SSH Key Configuration</h2>

<p align="center">### Copy the content of the public key and paste it into GitHub settings</p>

<a align="center">#### Visit: [GitHub SSH Key Settings] href="https://github.com/settings/keys"</a>

<p align="center">##### Click on "New SSH key," insert the key, give it a name, and click "Add SSH key"</p>

<p align="center">## Cloning a Repository</p>

- `git clone <repo-url>` - Clone a repository from the specified URL;
- `git clone <repo-url> <local-name>` - Clone a repository from the specified URL and name the local directory;

<h2 align="center">## Opening the Project in VSCode</h2>

- `code .` - Open the Visual Studio Code editor in the current directory;
- `code ~/path/to/your/directory` - Open the Visual Studio Code editor in the specified directory;
