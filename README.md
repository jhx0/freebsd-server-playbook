# freebsd-server-playbook

A simple Playbook to configure a new FreeBSD based server.

## Usage:
1. Clone/download this repository
2. Unpack/cd into the directory
3. Run
```
$ ansible-playbook -i hosts site.yml -Kk
```
4. The target will reboot when the playbook is finished running
5. Done

## Note:
Before running this Playbook, be sure to check the variables in the **group_vars** directory.  
Also: Make sure you have set the correct IP/Hostname in the **hosts** file.   
Take a look at the provided roles in the **site.yml** file!

**BEWARE:** do **_NOT_** run this Playbook blindly!
