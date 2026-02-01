# Claude Code Here — Windows Context Menu

Add "Claude Code here" to your Windows right-click menu with a simple .reg file.

Bonus: also disables the annoying Windows 11 "Show more options" submenu.


## Requirements

- Windows 10/11
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and in PATH


## Installation

1. Save  `claude-code-here.reg` somewere
2. Double-click to run it
3. Restart Explorer: `taskkill /f /im explorer.exe && start explorer`


## Uninstall
```reg
Windows Registry Editor Version 5.00

[-HKEY_CURRENT_USER\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}]
[-HKEY_CLASSES_ROOT\Directory\Background\shell\claude]
[-HKEY_CLASSES_ROOT\Directory\shell\claude]
```
