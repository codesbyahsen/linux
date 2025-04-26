# Install Multiple Node.js Versions on Ubuntu

## 1. Install nvm (Node Version Manager)
First, install nvm — the easiest tool to manage multiple Node.js versions:
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

Then, load nvm:
```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion" # This loads nvm bash_completion
```

Or simply close and reopen your terminal.

To verify that nvm is installed, run:
```bash
nvm --version
```

## 2. Install Multiple Node.js Versions
Now, install the Node.js versions you need.
For example, to install Node.js 16, 18, and 20:
```bash
nvm install 18
nvm install 20
nvm install 23
```

## 3. List Installed Versions
To see all the Node.js versions installed on your machine:
```bash
nvm ls
```

## 4. Switch Between Node.js Versions
You can easily switch between installed versions:
```bash
nvm use 20
```

## 5. Set a Default Node.js Version
To automatically use a specific version whenever you open a new terminal:
```bash
nvm alias default 23
```

## 6. Verify the Active Node.js Version
Check which version is currently active:
```bash
node -v
```

## 7. Uninstall a Node.js Version
To remove a specific version of Node.js:
```bash
nvm uninstall 20
```

## 8. Update nvm
To update nvm to the latest version, you can run:
```bash
nvm install --lts
```