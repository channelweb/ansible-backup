Backup
======

Backup role provides a backup utility that creates daily mysql dump and stores it to s3 folder.

Requirements
------------

An s3 bucket (where storing backup data) is required.
To use the role add these lines to `requirements.yml` file

    - src: https://github.com/channelweb/ansible-backup
      name: backup

Use `ansible-galaxy install -r requirements.yml` to add the role

Variables
---------

In `defaults/main.yml` you find default values for the variables you should set.

`tmp_backup_path` is the temporary folder on the server, where the backup archive is stored (before moving it to s3 folder). Default value is `/tmp/backup`.
`shell_script_path` is the path on the server where backup script will be stored. Default value is `/usr/local/bin`
`s3_backup_db_path` is the s3 bucket path where backup archive will be stored. Default values is `s3://bucketname/path`.

License
-------

BSD