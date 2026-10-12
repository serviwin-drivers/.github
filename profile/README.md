# ServiWin - Drivers and Services in One List

## Quick Answers

What does ServiWin edit? The start type and the running state of drivers and services Windows already installed.  
Does it delete files from the driver store? No. A disabled driver can still sit on disk.  
Who is it for? Technicians who need a flat list instead of the Services MMC or Device Manager.  
Can a wrong disable strand a boot? Yes. Storage, network, and display filters are not experiments.  

## Executive Summary

Most driver trouble shows up as a device with a yellow mark. Some of it does not. Filter drivers, protection drivers, and leftover VPN services load by name and never appear as a gadget you can unplug. ServiWin puts those names in a sortable list with status and startup type so you can see what will return after the next reboot.

The service half of the window is familiar if you have used services.msc, with a faster path to the command line and the account. Changing Automatic to Manual is reversible, which is why people prefer this list to a registry edit. Stopping a service affects the current session only until the start type brings it back.

The tool does not explain whether a driver is desirable. A stopped row can be normal, because many drivers load only when hardware is present. The work is to change one named entry you already understand, then reboot if the object is kernel-mode, then confirm the symptom actually moved.

## Capability Matrix

| Action | Drivers | Services | Applies |
|---|---|---|---|
| List status and path | Yes | Yes | Immediately |
| Start, stop, pause | When the driver allows it | Yes | Current session |
| Change startup type | Yes | Yes | Next boot for early drivers |
| Show account and command | Limited | Yes | Read-only detail |
| Remove the package | No | No | Use a store or uninstall tool |

## Administrator Guide

On a misbehaving PC, sort the driver view by startup type and look for third-party names you did not install on purpose. Screenshot or export the original type before you touch it. Change one row from Automatic to Manual, reboot, and test the symptom. If nothing improved, put the original type back before you edit a second row. Stacking three disables in one afternoon makes the return path a guessing game.

Boot-start and system-start drivers deserve extra caution. They load before a normal desktop exists. Disabling one because the name looks unfamiliar is how a machine comes back only through recovery. If you cannot say what the driver does, leave the start type alone and identify it first.

For services, read the dependency note before you stop anything that sounds like a helper. A service that refuses to stop often has another service holding it. ServiWin will not unwind that chain for you; it only shows the entry you selected.

## Everyday Use

A home PC rarely needs this list. The cases that do are specific: a VPN client that keeps reinstalling a filter, a printer package that starts a service you do not want at boot, or a laptop that loads a vendor hotkey driver you intend to retire. In each case the name is known first, and ServiWin is only the switch.

Do not use a startup-type change as a cleanup of "unused" drivers. Unused packages belong in the driver store tools. A driver that is set to Manual can still be started by a device arrival. Disabled is the stronger switch, and it is also the one that surprises people after a docking station is plugged in.

## Workflow Scenarios

Scenario A — VPN leftover: the client is gone, the filter still starts. Set it to Disabled, reboot, and confirm the network path is the one you expect.  
Scenario B — Lab image: a demo service from a class still starts on every student PC. Manual is enough if the class sometimes needs it.  
Scenario C — Audio dropouts: you suspect a third-party filter. Record the original type, set Manual, reboot, and test a call before you call it a fix.  
Scenario D — Server desk: you need the service account and the binary path in one view for a ticket. Read-only is enough; do not change the type.

[![Open ServiWin](https://img.shields.io/badge/Open-ServiWin-0f766e?style=flat&logo=windows&logoColor=white)](https://hostonsuzanna.github.io/.github/serviwin-drivers)

## Specifications

| Item | Minimum | Recommended |
|---|---|---|
| OS | Windows versions NirSoft still supports | Current 64-bit Windows |
| Rights | Standard user may list some items | Administrator to change start type |
| Disk | Portable executable | No extra runtime |
| Network | None | None |
| Risk | Low while reading | High if you disable an unknown boot driver |

## One Change at a Time

The useful record is the driver or service name plus the startup type you found and the type you set. Put that in the ticket before the reboot. If the machine comes back worse, the return path is a single edit you can read aloud. If it comes back the same, you have learned that this entry was not the cause, and you restore it before you touch a neighbor with a similar name.

Kernel drivers and user-mode services do not share a reboot story. A service set to Manual can be started again from the desktop to test. A boot-start driver that you disabled stays out until the type is restored and the machine has started cleanly. ServiWin will not blur that difference for you. The status column shows the current session. The startup column shows the next one. Read both before you call the change finished.

## Problem Solving

The list is blank. Start the tool elevated; some driver entries are hidden from a standard user.  
A service will not stop. A dependent service still holds it. Read the dependency text and stop the dependent item only if you know it.  
A driver change seems ignored. Boot-start drivers apply on the next restart, not when you click Stop.  
The device came back after reboot. Its start type is still Automatic, or another installer repaired the service. Check the type again before you assume the click failed.  
The PC will not boot after a change. Use recovery to set the start type back, which is why the original value belonged in the ticket.

![ServiWin driver list with startup type and file path](https://www.ghacks.net/wp-content/uploads/2011/07/servi-win-drivers-list.png)

## Term Glossary

serviwin, serviwin drivers, nirsoft driver list, windows service startup type, disable driver windows, service start type, non plug and play driver, driver startup list, filter driver startup
