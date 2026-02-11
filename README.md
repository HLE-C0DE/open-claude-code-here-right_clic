# Claude Code Here — Windows Context Menu

Add "Claude Code here" to your Windows right-click menu with a simple .reg file.

Bonus: also disables the annoying Windows 11 "Show more options" submenu.


## Requirements

- Windows 10/11
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed (CLI at `%USERPROFILE%\.local\bin\claude.exe`)


## Installation

1. Save  `claude_here.reg` somewhere
2. Double-click to run it
3. Restart Explorer: `taskkill /f /im explorer.exe && start explorer`


## Claude Desktop app conflict

If you also have the **Claude Desktop app** installed on Windows, the `claude` command in your PATH may resolve to the Electron desktop app instead of the Claude Code CLI. Symptoms include:

```
[ERROR:net\disk_cache\cache_util_win.cc:25] Unable to move the cache: Access denied
[ERROR:net\disk_cache\disk_cache.cc:236] Unable to create cache
```

This `.reg` file avoids the conflict by calling the CLI explicitly via `%USERPROFILE%\.local\bin\claude.exe` instead of the bare `claude` command.

If you still have issues, verify that the CLI is installed:
```
where claude
```
The CLI should be at `%USERPROFILE%\.local\bin\claude.exe`.


## Uninstall
```reg
Windows Registry Editor Version 5.00

[-HKEY_CURRENT_USER\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}]
[-HKEY_CLASSES_ROOT\Directory\Background\shell\claude]
[-HKEY_CLASSES_ROOT\Directory\shell\claude]
```
