# Windows 11 Classic Context Menu Registry Setup

This repository contains Windows Registry files to restore the full classic right-click context menu in Windows 11, bypassing the simplified menu introduced in the operating system. The provided `.reg` files allow you to enable the classic context menu for files, folders, and the desktop, or revert to the default Windows 11 menu.

## Purpose
The `RestoreClassicContextMenu.reg` file modifies the Windows Registry to:
- Display the full classic context menu immediately when right-clicking files, folders, or the desktop.
- Remove the need to select "Show more options" to access additional menu items.

The `RevertToWindows11Menu.reg` file restores the default Windows 11 simplified context menu.

## Prerequisites
- Windows 11 operating system.
- Administrator privileges to modify the Windows Registry.
- **Backup your system** or export the registry (`File > Export` in Registry Editor) before proceeding to avoid potential issues.

## Installation
1. **Apply the Classic Context Menu**:
   - Double-click `RestoreClassicContextMenu.reg`.
   - Click `Yes` when prompted by User Account Control (UAC).
   - Confirm the registry addition by clicking `Yes` in the Registry Editor prompt.
   - Restart Windows Explorer:
     - Press `Ctrl + Shift + Esc` to open Task Manager.
     - Locate `Windows Explorer`, right-click, and select `Restart`. Alternatively, reboot your PC.
   - Verify the change by right-clicking a file, folder, or the desktop. The full classic context menu should appear.

2. **Revert to the Default Windows 11 Menu (Optional)**:
   - Double-click `RevertToWindows11Menu.reg`.
   - Click `Yes` when prompted by UAC and confirm the registry change.
   - Restart Windows Explorer or reboot your PC to apply the reversion.

## File Structure
- `RestoreClassicContextMenu.reg`: Registry file to restore the classic context menu.
- `RevertToWindows11Menu.reg`: Registry file to revert to the default Windows 11 simplified context menu.

## Troubleshooting
- **Classic menu not appearing**: Ensure you have administrator privileges and that the `.reg` file was applied successfully. Restart Windows Explorer or reboot your PC.
- **System issues**: If problems occur, use `RevertToWindows11Menu.reg` to restore the default menu. Restore your registry backup if necessary.
- **Manual Verification**: To confirm the change manually, check the registry at:
  - Path: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Shell Extensions\Blocked`
  - Ensure the `{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}` key is present for the classic menu or absent for the default menu.

## Notes
- **Temporary Access**: Hold `Shift` while right-clicking to access the classic context menu without applying permanent changes.
- To make the classic menu appear only in the extended context menu (Shift + right-click), modify the `.reg` file to include `"Extended"=""` in the relevant registry key.

## Warning
- Modifying the Windows Registry can cause system issues if done incorrectly. Proceed with caution and ensure you have a registry backup.
- This script is designed for Windows 11 only.

## License
This project is provided as-is, with no warranty. Use at your own risk.
