# Installing and Configuring Cursor AppImage on Ubuntu 24.04

## 1. Download the AppImage
- Go to the [Cursor website](https://www.cursor.com/downloads).
- Download the AppImage file for Linux (X64).

## 2. Move Image in Appropirate Directory & Make the AppImage Executable
```bash
sudo mv ~/Downloads/Cursor-0.49.6-x86_64.AppImag /.local/bin/appimages/
```

Make the AppImage executable:
```bash
sudo chmod +x ~/.local/bin/appimages/Cursor-0.49.6-x86_64.AppImage
```

## 3. Create a Desktop Entry
```bash
sudo nano ~/.local/share/applications/cursor.desktop
```
Add the following content to the file:
```ini
[Desktop Entry]
Name=Cursor
Comment=Cursor AI
Exec=/home/username/.local/bin/appimages/Cursor-0.49.6-x86_64.AppImage
Icon=/home/username/.local/share/icons/cursor.png
Categories=Development;IDE;
StartupNotify=true
Terminal=false
Type=Application
```
Replace `username` with your actual username.

## 4. Add Icon
- Download the icon from the [Cursor website](https://www.cursor.com/downloads).
- Save it in the `~/.local/share/icons/` directory as `cursor.png`.
```bash
sudo mv ~/Downloads/cursor.png ~/.local/share/icons/
```

## 5. Update Desktop Database
```bash
update-desktop-database ~/.local/share/applications
```

## 6. Launch Cursor
- You can now launch Cursor from the applications menu or by running:
```bash
~/.local/bin/appimages/Cursor-0.49.6-x86_64.AppImage
```

## 7. Uninstalling Cursor
To uninstall Cursor, simply delete the AppImage and the desktop entry:
```bash
sudo rm ~/.local/bin/appimages/Cursor-0.49.6-x86_64.AppImage
sudo rm ~/.local/share/applications/cursor.desktop
sudo rm ~/.local/share/icons/cursor.png
```

