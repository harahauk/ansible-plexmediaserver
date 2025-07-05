ansible-plexmediaserver
=======================
```diff
# Project maturity (- Dev|@ Staging|+ Prod):
@ Staging
```

An [Ansible](https://www.ansible.com/)-role which installs and configures `Plex Media Server` on the target hosts.  
Optionally install these plugins:  
- [Absolute Media Scanner](https://github.com/ZeroQI/Absolute-Series-Scanner)
- [Hama.bundle](https://github.com/ZeroQI/Hama.bundle)
- [PlexTraktSync](https://github.com/Taxel/PlexTraktSync)


Requirements
------------

## Linux
Currently supports following distributions  
- RHEL-based (RockyLinux, AlmaLinux)

## Ansible
You need Ansible installed on the control-node to run this node. **#TODO:** Instructions are often included in my other
roles


Role Variables
--------------
| Variable                          | Mandatory | Default   | Description |
| --------------------------------- | --------- | --------- | ----------- |
| plex_install_plugins              | no        | yes       | Decides if the extra plugins (and dependencies) mentioned above should be installed or not |
| plex_perform_system_wide_upgrade  | no        | yes       | Upgrades 'all' packages using the package-manager, useful
when the server is running only plex and you'd like to get all maintenancy done |


Dependencies
------------
This role might "work" on a wide range of Linux-distributions, but below are the distros that are actually tested.

xor:
  - AlmaLinux 9


Example Playbook
----------------
```yaml
- hosts: plexmediaserver_group
  roles:
  - ansible-plexmediaserver    # Change to the folder-name to which this Git-checkout resides
  vars:
    plex_install_plugins: no
```

Author Information
------------------

[Harald Hauknes](https://github.com/harahauk)

License
-------

MIT License

See [LICENSE](./LICENSE) for the full text.
