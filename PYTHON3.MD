# How to Install Multiple Python Versions Using Pyenv in Ubuntu 24.04

## 1. Update the Package Index
Before installing any new package, it's a good practice to update the local package index:

```bash
sudo apt update
```

## 2. Install Required Dependencies
To install `pyenv`, you need to install some dependencies. Run the following command:

```bash
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
  libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
  libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev
```

## 3. Install Pyenv
```bash
curl https://pyenv.run | bash
```
It will install pyenv, pyenv-virtualenv, and other useful plugins.

## 4. Configure Shell
Edit your ~/.bashrc (or ~/.zshrc if you're using zsh) and add at the bottom:
```bash
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init --path)"
eval "$(pyenv virtualenv-init -)"
```
Then reload your shell:
```bash
exec "$SHELL"
```

## 5. Install Python Versions
You can now install different Python versions using `pyenv`. For example, to install Python 3.10.0 and 3.11.0, run:
```bash
pyenv install 3.10.0
pyenv install 3.11.0
pyenv install 3.13.0
```
(it will compile and set up cleanly in your $HOME/.pyenv/versions/)
All versions installed — no system impact!

## 6. Set Global Python Version
You can set a global Python version that will be used by default:
```bash
pyenv global 3.10.0
```
You can check the current global Python version with:
```bash
pyenv global
```

## 7. Set Local Python Version
You can also set a local Python version for a specific project directory:
```bash
cd /path/to/your/project
pyenv local 3.11.0
```
This will create a `.python-version` file in the project directory, which specifies the Python version to use when you are in that directory.

## 8. Verify Installation
You can verify that the correct Python version is being used by running:
```bash
python --version
```
This should return the version of Python you set as global or local.

## 9. Install Python Packages
You can now install Python packages using `pip` as usual. For example:
```bash
pip install requests
```
This will install the `requests` package for the currently active Python version.

## 10. Uninstall Python Versions
If you want to uninstall a specific Python version, you can do so with:
```bash
pyenv uninstall 3.10.0
```
This will remove the specified version from your system.

## Conclusion
You have successfully installed multiple Python versions using `pyenv` on Ubuntu 24.04. You can now easily switch between different Python versions for your projects without any conflicts.

## Additional Notes
- You can list all installed Python versions with:
```bash
pyenv versions
```
- You can also check the available Python versions that can be installed with:
```bash
pyenv install --list
```