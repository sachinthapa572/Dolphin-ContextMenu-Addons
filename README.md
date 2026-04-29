# Dolphin Context Menu Addons

Easily add "Edit with" or "Open with" entries to the Dolphin context menu for any application, such as VS Code, VS Code Insiders, Zed, Ghosty, a terminal, or any custom tool.

## Repository Layout

The service-menu files are grouped by application so the repository stays easy to scan as more entries are added.

```text
.
├── README.md
└── ide/
    ├── vscode/
    │   ├── edit-with-vscode.desktop
    │   └── open-with-vscode.desktop
    ├── vscode-insiders/
    │   ├── edit-with-vscode-insiders.desktop
    │   └── open-with-vscode-insiders.desktop
    └── zed/
        ├── edit-with-zed.desktop
        └── open-with-zed.desktop
```

## Installation

1. Download the **.desktop** files from this repository or the [KDE Store](https://store.kde.org/p/2346389/).
2. Move them to the service menus directory:
   - **Plasma 6**: `~/.local/share/kio/servicemenus/`
   - **Plasma 5**: `~/.local/share/kservices5/ServiceMenus/`

If you clone the repository, copy the `.desktop` files from the app folders under `ide/` into the matching service menus directory.

## Customization

You can adapt these files for any application by editing the `.desktop` file in a text editor:

- **Exec**: The command to run (e.g., `code %F` for VS Code, `ghosty %F` for Ghosty).
- **Icon**: The icon name or path.
- **Name**: The text that will appear in your context menu.

### Example for VS Code:

```ini
[Desktop Action openvscode]
Exec=code %F
Icon=com.visualstudio.code
Name=Open with VS Code
```

### Example for VS Code Insiders:

```ini
[Desktop Action openvscodeinsiders]
Exec=code-insiders %F
Icon=com.visualstudio.code
Name=Open with VS Code Insiders
```

### Example for Ghosty:

```ini
[Desktop Action openghosty]
Exec=ghosty %F
Icon=com.mitchellh.ghosty
Name=Open in Ghosty
```

### Example for Zed:

```ini
[Desktop Action openzed]
Exec=zed %F
Icon=zed
Name=Open with Zed
```

## Troubleshooting

**If the entries do not appear** or you receive a "not authorized" error, make the files executable:

```bash
# For Plasma 6
chmod +x ~/.local/share/kio/servicemenus/*.desktop

# For Plasma 5
chmod +x ~/.local/share/kservices5/ServiceMenus/*.desktop
```

Restart Dolphin for the changes to take effect.
