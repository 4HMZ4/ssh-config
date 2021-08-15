# ssh-config
my ssh-config with security in mind

## changes made according to this guide.
https://www.informaticar.net/security-hardening-ubuntu-20-04/

## install:
* sudo apt-get install fail2ban

## sshd-config
* Protocol 2
* Port 2222
* PermitRootLogin no
* MaxAuthTries 5
* ClientAliveInterval 180
* AllowUsers ahmza
