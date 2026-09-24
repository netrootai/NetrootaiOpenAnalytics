# Netroot AI Windows Installer Guide

This guide explains how to install and open Netroot AI on Windows.

## Before You Install

You need:

- Windows 10 or Windows 11, 64-bit
- Administrator access on the computer
- A valid Netroot AI account on `netrootai.app`
- The Netroot AI Windows installer, usually named something like `netrootai_13.0.2_local_windows_amd64_unsigned_setup.exe`

Because the installer is currently unsigned, Windows may show a security warning. That is expected for this build.

## Install Netroot AI

1. Download the installer to your Windows computer.
2. Right-click the installer and choose **Run as administrator**.
3. If Windows SmartScreen appears, click **More info**, then **Run anyway**.
4. Follow the installer prompts.
5. When installation finishes, Netroot AI should be installed and started as a Windows service.

## Open Netroot AI

After installation, open your browser and go to <http://127.0.0.1:3005>.

Netroot AI is only available locally on the computer where it is installed. It listens on `127.0.0.1`, which means other devices on your network cannot access it directly.

## Sign In

To use the app, sign in with a valid Netroot AI account from <https://netrootai.app>.

If you do not already have access to Netroot AI, create or obtain an account first. The Windows app depends on that account for authentication.

## If Netroot AI Does Not Open

First, wait 30–60 seconds after installation, then refresh <http://127.0.0.1:3005>.

If it still does not load:

1. Open the Windows Start menu.
2. Search for `Services`.
3. Open the Services app.
4. Look for `Netroot AI`.
5. Make sure the service is running.
6. If it is stopped, right-click it and choose **Start**.

You can also right-click the service and choose **Restart**.

## If Port 3005 Is Already In Use

Netroot AI uses local port `3005`. If another application is already using that port, Netroot AI may not start correctly.

To check from PowerShell:

```powershell
Get-NetTCPConnection -LocalAddress 127.0.0.1 -LocalPort 3005
```

If another app is using the port, close that app and restart the `Netroot AI` service.

## Uninstall Netroot AI

To uninstall:

1. Open Windows Settings.
2. Go to **Apps**.
3. Find **Netroot AI**.
4. Click **Uninstall**.
5. Follow the prompts.

After uninstalling, restart Windows if prompted.
