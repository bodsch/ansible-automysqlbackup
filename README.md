
# Ansible Role:  `automysqlbackup`

Installs and confige automysqlbackup script.


[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/bodsch/ansible-automysqlbackup/main.yml?branch=main)][ci]
[![GitHub issues](https://img.shields.io/github/issues/bodsch/ansible-automysqlbackup)][issues]
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/bodsch/ansible-automysqlbackup)][releases]
[![Ansible Quality Score](https://img.shields.io/ansible/quality/50067?label=role%20quality)][quality]

[ci]: https://github.com/bodsch/ansible-automysqlbackup/actions
[issues]: https://github.com/bodsch/ansible-automysqlbackup/issues?q=is%3Aopen+is%3Aissue
[releases]: https://github.com/bodsch/ansible-automysqlbackup/releases
[quality]: https://galaxy.ansible.com/bodsch/automysqlbackup


## Operating systems

Tested on

* Arch Linux
* Debian based
    - Debian 10 / 11
    - Ubuntu 20.10


## Contribution

Please read [Contribution](CONTRIBUTING.md)

## Development,  Branches (Git Tags)

The `master` Branch is my *Working Horse* includes the "latest, hot shit" and can be complete broken!

If you want to use something stable, please use a [Tagged Version](https://github.com/bodsch/ansible-automysqlbackup/tags)!


## usage

```yaml
automysqlbackup_version: 3.0.7

automysqlbackup_pre_script:
  file: ''
  content: ''

automysqlbackup_post_script:
  file: ''
  content: ''

automysqlbackup_backup_directory: /srv/backup/mysql

automysqlbackup_git:
  repository: 'https://github.com/bodsch/AutoMySQLBackup.git'
  version: master

automysqlbackup_dump:
  username: ''
  password: ''
  host: ''
  socket: /run/mysqld/mysqld.sock
  create_database: true
  single_transaction: true
  full_schema: true
  dbstatus: true
  login_path_file: ''
  use_separate_dirs: true

automysqlbackup_multicore: false
automysqlbackup_multicore_threads: 2

automysqlbackup_rotation:
  daily: 6
  weekly: 12
  monthly: 3

automysqlbackup_exclude_databases:
  - performance_schema
  - information_schema

automysqlbackup_include_databases: []

automysqlbackup_cron:
  enable: true
  minute: '58'
  hour: '02'

automysqlbackup_backup_local_files: []
```

### use a pre running script

```yaml
automysqlbackup_pre_script:
  file: '/tmp/pre.sh'
  content: |
  #!/bin/bash
  echo "foo"
```


## Author and License

- Bodo Schulz

## License

[Apache](LICENSE)

**FREE SOFTWARE, HELL YEAH!**


