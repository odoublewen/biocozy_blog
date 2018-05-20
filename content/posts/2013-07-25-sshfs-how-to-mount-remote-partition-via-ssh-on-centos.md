+++
title = "SSHFS: How to Mount Remote Partition via SSH on CentOS"
slug = "2013-07-25-sshfs-how-to-mount-remote-partition-via-ssh-on-centos"
published = 2013-07-25T12:59:00.003000-07:00
author = "Owen"
tags = []
+++
This is hugely helpful for anyone wanting mount-point accessible files
over SSH.   
  
Don't bother with fstab or the mount command.  Full instructions
[here](http://www.centosblog.com/sshfs-how-to-mount-remote-partition-via-ssh-on-centos/),
and the executive summary is:  
  

    yum install fuse sshfs

    sshfs user@remote_host:/remote_directory /local_mount_partition
