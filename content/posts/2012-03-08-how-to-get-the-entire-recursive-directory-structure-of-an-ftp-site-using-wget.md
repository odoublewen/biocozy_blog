+++
title = "How to get the entire recursive directory structure of an FTP site\nusing wget"
slug = "2012-03-08-how-to-get-the-entire-recursive-directory-structure-of-an-ftp-site-using-wget"
published = 2012-03-08T01:25:00.001000-08:00
author = "Owen"
tags = []
+++
How can I use wget to get a recursive directory listing of an entire FTP
site?

yes, wget --no-remove-listing ftp://myftpserver/ftpdirectory/ will get
and retain a directory listing for a single directory (which was
discussed
[here](http://stackoverflow.com/questions/7261140/wget-only-the-file-names-in-an-ftp-directory))

but, wget -r --no-remove-listing ftp://myftpserver/ftpdirectory/ will
recurse and download an entire site

so, if you want to get the recursive directory structure, but not
download the entire site, try wget -r --no-remove-listing --spider
ftp://myftpserver/ftpdirectory/
