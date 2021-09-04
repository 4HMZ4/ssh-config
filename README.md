# ssh-config
my ssh-config with security in mind

## changes made according to this guide.
https://www.informaticar.net/security-hardening-ubuntu-20-04/

## install:
* sudo apt-get install fail2ban

## sshd-config
/etc/ssh/sshd-config
* Protocol 2
* Port 2222
* PermitRootLogin no
* MaxAuthTries 5
* PasswordAuthentication no
* PermitEmptyPasswords no
* AllowUsers ahmza
* ClientAliveInterval 180

## jail.local
/etc/fail2ban/jail.local
* [DEFAULT]
* bantime = 8h
* ignoreip = 127.0.0.1/8 192.168.10.20 192.168.10.30
* ignoreself = true
* [sshd]
* enabled = true
* port = 2222
* filter = sshd
* logpath = /var/log/auth.log
* maxretry = 3
