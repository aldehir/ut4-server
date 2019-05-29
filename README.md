# UT4 Server Ansible Role

Ansible role for setting up a UT4 server.


## Example Playbook

```yaml
---
- hosts: 127.0.0.1
  connection: local
  become: yes

  roles:
    - name: ut4-server
      vars:
        - rcon_password: "<set rcon password>"
```

## Administration

### Configuration

The role creates a system account for running the UT4 server, the account is
`ut4-server` by default. Below are the default directory paths.

* User home directory: `/srv/ut4-server`
* Server directory: `/srv/ut4-server/LinuxServer`
* Configuration directory: `/srv/ut4-server/LinuxServer/UnrealTournament/Saved/Config/LinuxServer`


### Service

This role creates a systemd service unit, `ut4-server.service`. The service is
enabled by default.

Below are a few commands to manage the service.  

    # systemctl status ut4-server
    # systemctl start ut4-server
    # systemctl stop ut4-server
    # systemctl restart ut4-server

If you need better logs,

    # journalctl -u ut4-server
