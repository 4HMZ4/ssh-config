# ssh-config
my ssh-config with security in mind

## changes made accoring to this guide.
https://www.informaticar.net/security-hardening-ubuntu-20-04/

## install:
* sudo apt install libpam-google-authenticator

## sshd-config
* Protocol 2
* Port 2222
* PermitRootLogin no
* MaxAuthTries 5
* ClientAliveInterval 180
* AllowUsers ahmza
* ChallengeResponseAuthentication yes
* AuthenticationMethods publickey,password publickey,keyboard-interactive

## /etc/pam.d/sshd
* auth required pam_google_authenticator.so
* auth required pam_permit.so

## Run
* google-authenticator
  * Time-based tokens – y
  * update .google_authenticator file – y
  * Dissalow multiple uses – y
  * Permit shew of up to 4 minutes – n
  * Enable rate limiting – y
