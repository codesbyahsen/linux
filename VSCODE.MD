# Visual Studio Code Installation Guide for Linux (Ubuntu)

## Option 1: Install .DEB Package from Official Website
1. Download the latest .deb package from the [official Visual Studio Code website](https://code.visualstudio.com/).
2. Open a terminal and navigate to the directory where the .deb file is downloaded.
3. Install the package using the following command:

Before installing any new package, it's a good practice to update the local package index:

```bash
sudo apt update
```

Then, install the downloaded .deb package:
```bash
sudo dpkg -i code_*.deb
```

<br>
<br>

## Option 2: Install via Snapstore
Before installing any new package, it's a good practice to update the local package index:

```bash
sudo apt update
```

Run the following command to install Visual Studio Code via Snap:

```bash
sudo snap install --classic code
```