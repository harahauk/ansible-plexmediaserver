ansible-plexmediaserver
=======================
**NOTE**: This is one of my oldest roles and currently is only avaialbe for testing  
**NOTE2**: Plex has become notoriosly bas at Anime, I havent noticed sice I havent really been into it for a few years, but looking at
alternatives  
**NOTE3**: It
n truth best to skio this one altogether while I either fix it or ditch it.

```diff
# Project maturity (- Dev|@ Staging|+ Prod):
@ Staging
```

An [Ansible](https://www.ansible.com/)-role which installs and configures `Plex Media Server` on the target host(s).
It optionally install these plugins suitable for handling Anime-content:
- [Absolute Media Scanner](https://github.com/ZeroQI/Absolute-Series-Scanner)
- [Hama.bundle](https://github.com/ZeroQI/Hama.bundle)
- [PlexTraktSync](https://github.com/Taxel/PlexTraktSync) NOTE: Being discontinued


Requirements
------------

## Linux
Currently supports following distributions
- RHEL-based
  - RockyLinux 9
  - AlmaLinux 9

## Ansible
You need Ansible installed on the control-node to run this node. **#TODO:** Instructions are often included in my other
roles


Role Variables
--------------
| Variable                          | Mandatory | Default   | Description |
| --------------------------------- | --------- | --------- | ----------- |
| plex_install_plugins              | no        | no       | Decides if the extra plugins (and dependencies) mentioned above should be installed or not |
| plex_perform_system_wide_upgrade  | no        | yes       | Upgrades 'all' packages using the package-manager, useful
when the server is running only plex and you'd like to get all maintenancy done |


PlexTraktSync
-------------
Note: Is now a paid feautre since 2026-08-18
Reacting to `CRITICAL Error running sync command: Trakt error: Unable to refresh token`
- `plextraktsync plex-login`
- `plextraktsync trak-login`


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
