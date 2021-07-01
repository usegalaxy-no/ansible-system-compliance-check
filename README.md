# ansible-system-compliance-check
=========

Test services and configuration on the server nodes (routinely and as part of a manual check after reboot)
Just a check playbook, no changes to the systems.





Requirements
------------
- ansible
- root permissions on the destination hosts


Variables
--------------
defined in group_vars/GROUPNAME.yml , Group name refers to the entries in the hosts.inv


Dependencies
------------

manual execution
----------------


```
[~]> ansible-playbook site-checks.yml
```



check modules
----------------

001-mounts

- NFS mounts
- cvmfs mounts


002-services

- standard system services
- services related to galaxy (galaxy, nga, nginx)
- additional services (slurm, docker)
- check if autofs is disabled on slurm nodes



003-ports

- open tcp ports, which are required for the services (check from localhost only)