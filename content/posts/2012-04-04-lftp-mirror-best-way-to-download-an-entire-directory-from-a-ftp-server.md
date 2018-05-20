+++
title = "lftp mirror: best way to download an entire directory from a FTP server"
slug = "2012-04-04-lftp-mirror-best-way-to-download-an-entire-directory-from-a-ftp-server"
published = 2012-04-04T03:07:00-07:00
author = "Owen"
tags = []
+++
As much as I hate FTP, there situations where one must use it.  I
finally have settled on the best way to get an entire directory, with
recursive file retrieval:

lftp -e "mirror dir1/subdir2/subdir3" -u username,password
ftphost.domain.com

Of course, [FTP must die](http://mywiki.wooledge.org/FtpMustDie), but
until then, I am glad there is [lftp](http://lftp.yar.ru/).
