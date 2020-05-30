# backupsend
Script for creating ZFS snapshots and sending those to a slave server

```
Usage: backupsend [(-s|--suffix) <suffix>] [(-i|--identity-file) <identity_file>] <filesystem> <remote_host>

Creates zfs snapshot with current date and optionally, suffix; Sends it to remote_host.
Filesystem names should be equal.
Warning: snapshots are applied with -F on target host

Parameters:
    -s|--suffix <suffix>               add suffix to snapshot name
    -i|--identity-file <identity_file> use this identity file for ssh
    -p|--progress                      use pv to display progress
    -l|--lines                         print progress every line

Examples:
  Create snapshot mypool/myfs@2020-01-01-weelkly and upload it to host.org using custom rsa key
    backupsend -s -weelkly -i /root/.ssh/id_backup.rsa mypool/myfs root@host.org
```
