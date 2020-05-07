[![Build Status](https://travis-ci.com/Mireiawen/ansible-role-solarwinds-papertrail.svg?branch=master)](https://travis-ci.com/Mireiawen/ansible-role-solarwinds-papertrail) [![Ansible Galaxy](https://img.shields.io/badge/Ansible%20Galaxy-mireiawen.solarwinds-papertrail-blueviolet)](https://galaxy.ansible.com/mireiawen/solarwinds-papertrail)


# Solarwinds Papertrail

Install [Solarwinds Papertrail](https://www.papertrail.com/) logging. Should work with most distributions with Rsyslog installed, automated tests are run on Debian and Ubuntu.

## Requirements

Rsyslogd and Papertrail account.

## Role Variables

### Solarwinds settings
#### log_server
The log server hostname you get from the Solarwinds Papertrail. It should look like `logsX.papertrailapp.com`.

#### log_port
The log server port you get from the Solarwinds Papertrail.

### Common settings
#### log_config_owner
The owner for the configuration file created. Defaults to `root`.

#### log_config_group
The group for the configuration file created. Defaults to `root`.

#### log_config_mode
The permissions for the configuration file created. Defaults to `u=rw,go=r`.

### Rsyslogd specific settings
#### rsyslog_config_dir
The folder to write the Papertrail configuration to. Defaults to `/etc/rsyslog.d`.

#### rsyslog_config_file
The file to write the Papertrail configuration to. Defaults to `{{ rsyslog_config_dir }}/95-papertrail.conf`.

#### rsyslog_config_main
The main Rsyslog configuration to check for, used to check Rsyslog existence. Defaults to `/etc/rsyslog.conf`.

#### rsyslog_service
The Rsyslog service name. Defaults to `rsyslog`.

## Dependencies

None.

## Example Playbook

```
- hosts: "servers"
  roles:
  - "mireiawen.solarwinds-papertrail"
    log_server: "logsX.papertrailapp.com"
    log_port: "12345"
```

## License
MIT, see `LICENSE`
