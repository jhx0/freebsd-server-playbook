# freebsd-server-playbook

A simple **Playbook** to configure a new **FreeBSD** based server.

## Requirements:
To run this **Playbook** on a **FreeBSD** system, the system in question must have **Python** installed.
This can be done via **pkg** for example:
```Shell
target# pkg install python
```

## Usage:
1. Clone/download this repository
2. Unpack/cd into the directory
3. Run
```
$ ansible-playbook main.yml (-Kk)
```
4. The target will reboot when the playbook is finished running
5. Done

## Examples
All tasks can be selected via **Tags**, so you can pick whatever tasks you want to run.   
Following, a couple of use cases:
1. Run all tasks
```Ansible
$ ansible-playbook main.yml --tags all (-Kk)
```
2. Only run a subset of tasks
```Ansible
ansible-playbook main.yml --tags "upgrade,doas,sshd,loader,ports" (-Kk)
```
3. Run only one task
```
ansible-playbook main.yml --tags "fail2ban" (-Kk)
```
All available **Tags**:
```Shell
upgrade
ntp
pkg
login_conf
rc
doas
packages
sshd
sysctl
fail2ban
hushlogin
loader
ports
reboot
```

## Note:
Before running this Playbook, be sure to check the variables in the **vars/main.yml** directory.  
Also: Make sure you have set the correct IP/Hostname in the **hosts** file.   

**BEWARE:** do **_NOT_** run this Playbook blindly!

## Thanks:
**Juraj „otis“ Lutter** (https://twitter.com/jurajlutter) - For suggesting to only rebuild the login.conf db when necessary.
