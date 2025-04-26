# Install Multiple Python Versions on Ubuntu

## 1. Update the Package Index
Before installing any new package, it's a good practice to update the local package index:

```bash
sudo apt update
```

## 2. Install Required Dependencies
Install dependencies required for adding a PPA and building Python:
```bash
sudo apt install software-properties-common -y
```

## 3. Add the Deadsnakes PPA
The Deadsnakes PPA provides newer Python versions for Ubuntu:
```bash
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
```

## 4. Install Multiple Python Versions
Now install the Python versions you need. For example, to install Python 3.9, 3.10 and 3.11:
```bash
sudo apt install python3.9 python3.10 python3.11 -y
```

## 5. Configure update-alternatives for Python
Tell the system about the installed Python versions:
```bash
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.9 1
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 2
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.11 3
```

## 6. Switch Between Python Versions
You can switch between the installed Python versions using:
```bash
sudo update-alternatives --config python3
```
You will see a list of installed Python versions. Enter the selection number for the version you want to use.

## 7. Verify the Active Python Version
To check the currently active Python version, run:
```bash
python3 --version
```
This command should return the version of Python that is currently set as default.

## 8. Install pip for Each Python Version
You may need to install pip for each Python version separately. For example:
```bash
sudo apt install python3.9-venv python3.9-distutils
sudo apt install python3.10-venv python3.10-distutils
sudo apt install python3.11-venv python3.11-distutils
```

