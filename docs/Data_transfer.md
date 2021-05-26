# Data_transfer

[TOC]

This note is for how to transfer data from local to remote, or between two servers.

## SCP

SCP is useful when transfer data between two server using ssh protocol.

```
scp -r <username@remote_host>:<remote directory> <local directory>

# For example
scp -r wangye@192.168.38.73:/mnt/ntfs1/tanpeng26034/X101SC19030851_panda_Data_Release_20210225 /mnt/raw_data/data_wangye/DNA
```

## rsync

`rsync` is a remote and local file synchronization tool. It uses an algorithm that minimizes the amount of data copied by only moving the portions of files that have changed.

### Synchronization between two local folder 

```
rsync -a <dir1/> <dir2>
```

!!! Note

        The "/" after the first directory is necessery.


### Dry run before starting rsync commands

The `-n` or `--dry-run` options give you the chance to double-check your argument and commands before you run it formally.

```
rsync -anv <dir1/> <dir2>
```

### Sync with remote server

This is similar with `scp`. But `scp` is preferred by day to day work, while `rsync` is preferred by recurring tasks which need to be repeated for a certain time.

But, `scp` can be used to transfer data between two remote servers, which `rsync` is only allow to transfer data from local to remote server.

```
rsync -a <username@remote_host>:<remote directory> <local directory>
```

`-P` flag is very help as it allows you to resume job is it interrupped accidently. It also can give you a progress bar to track the progress intutively.

```
rsync -aPv <username@remote_host>:<remote directory> <local directory>
```

However, if the port is not 21 or 22, you need to specify the remote port by yourself. Here is the example.

```
rsync -aPv -e 'ssh -p 9222' /mnt/raw_data/ WangYe@192.168.3.134:/home/WangYe/data_back_up

```





