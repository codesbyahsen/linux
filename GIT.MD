# Git Installation Guide for Linux (Ubuntu)

## 1. Update the Package Index
Before installing any new package, it's a good practice to update the local package index:

```bash
sudo apt update
```

## 2. Install Git
To install Git, run the following command:
```bash
sudo apt install git -y
```
This command will install the latest version of Git available in the Ubuntu repositories.

## 3. Verify the Installation
After the installation is complete, you can verify that Git was installed successfully by checking its version:

```bash
git --version
```
This command should return the version of Git that was installed, confirming that the installation was successful.

<br>
<br>

## Basic Git Setup (Recommended)
After installing Git, it’s recommended to configure your name and email address, which will be used for your commits.

Set your username:
```bash
git config --global user.name "Your Name"
```
Set your email address:
```bash
git config --global user.email "your.email@example.com"
```

You can verify your Git configuration with:
```bash
git config --list
```
This command will display all the Git configuration settings, including the username and email you just set.
## Additional Configuration (Optional)
You may also want to set up a default text editor for Git. For example, to set Nano as your default editor, run:
```bash
git config --global core.editor "nano"
```
Or, to set Vim as your default editor:
```bash
git config --global core.editor "vim"
```
Or, to set VS Code as your default editor:
```bash
git config --global core.editor "code --wait"
```
## Conclusion
You have successfully installed Git on your Ubuntu system and configured it with your name and email address. You can now start using Git for version control in your projects.