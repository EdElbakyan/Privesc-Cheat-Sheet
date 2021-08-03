# Windows Privesc Cheat-Sheet

## User Enumeration

User info - ``` whoami ```

User privs -  ``` whoami /priv ```

User groups - ```  whoami /groups ```

Users on machine -  ``` net user ```

Info about a specific user - ``` net user 'user'```

Local groups - ```net localgroup```

## Network Enumeration

Ip - ``` ipconfig /all```

Arp table - ``` arp -a ```

Routing table - ``` route print ```

Communications - ``` netstat -nao```

## Service Enumeration
Query the config of service - ```sc qc <service>```
	
Query the current status of service - ```sc query <service>```

Modify a config of a service - ```sc config <name> <option>```

Start/Stop a service - ```net start/stop <name>```

List scheduled task - ```schtasks /query /fo LIST /v ```

List tasks - ```tasklist```

## Password Hunting

find password strings - ```findstr /si password *.txt *.ini *.config ```


