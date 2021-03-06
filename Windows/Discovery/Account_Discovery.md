﻿## Account Discovery

MITRE ATT&CK Technique: [T1087](https://attack.mitre.org/wiki/Technique/T1087)

## Test Script

[Discovery](https://github.com/redcanaryco/atomic-red-team/tree/master/Windows/Payloads/Discovery.bat)

### Net.exe

Domain Group Enumeration:

    net groups "domain administrators" /domain

Domain User Enumeration:

    net user <username> /domain

Local Group Enumeration:

    net localgroup "administrators"

Local User Enumeration:

    net user

Input:

    net use

Input:

    net share

Input:

    net view

Input:

    net accounts

## wmic.exe

### Reconnaissance

Input:

    wmic useraccount get /ALL

Input:

    wmic useraccount list

Input:

    wmic startup list brief

Input:

    wmic share list

Input:

    wmic service get name,displayname,pathname,startmode

Input:

    wmic process list brief

Input:

    wmic process get caption,executablepath,commandline

Input:

    wmic qfe get description,installedOn /format:csv

Input:

    wmic /node:"192.168.0.1" service where (caption like "%sql server (%")

Input:

    get-wmiobject –class "win32_share" –namespace "root\CIMV2" –computer "targetname"
