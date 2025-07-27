---
title: Initiate Windows 11 Offline without a Microsoft Account
categories: 02-Tips
---

There were several ways to avoid internet connecting when first starting Windows 11 which is invalid now:
  - stop "Network Connection Flow" in task manager.
  - use "OOBE \BypassNRO" command.

And the only 2 method to do that currently(23.7) is that:

Change Registry when installing:
  - Open cmd with Shift+F10 or Shift+Fn+F10.
  - Input "regedit" and press enter.
  - Find "Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion|OOBE" directory.
  - Create a new DWORD(D) item named "BypassNRO" and set its value to 1.
  - In cmd windows, input logoff and press enter to restart computer.
  - Then "no internet" can be seleted, and create a local account to login Windows 11.

Or use Rufus to disable internet requirement before create the bootable USB installation media.