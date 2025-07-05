ansible-plexmediaserver
=======================
```diff
# Project maturity (- Dev|@ Staging|+ Prod):
@ Staging
```

An [Ansible](https://www.ansible.com/)-role which installs and configures `Plex Media Server` on the target hosts.
Optionally install the plugins
- [Absolute Media Scanner]
- [Hama.bundle]
- [PlexTraktSync]


Requirements
------------

## Linux
Currently supports following distributions
- RHEL-based (RockyLinux, AlmaLinux)

## Ansible
You need Ansible installed on the control-node to run this node. #TODO: Instructions


Role Variables
--------------
| Variable              | Mandatory | Default   | Description |
| --------------------- | --------- | --------- | ----------- |
| plex_install_plugins  | no        | yes       | Whether the extra plugins mentioned above should be installed or not |



Dependencies
------------
This role might "work" on a wide range of Linux-distributions, but below are the distros that are actually tested.

xor:
  - AlmaLinux 9


Example Playbook
----------------
```
- hosts: plexmediaserver_group
  roles:
  - ansible-plexmediaserver    # Change to the folder-name to which this Git-checkout resides
  vars:
    plexmediaserver_user: "my_unprivileged_user"
```

Author Information
------------------

[Harald Hauknes](https://github.com/harahauk)

License
-------

MIT License

See [LICENSE](./LICENSE) for the full text.
