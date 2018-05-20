+++
title = "Package search tools: \"provided by\" and \"what provides\""
slug = "2011-08-08-package-search-tools-provided-by-and-what-provides"
published = 2011-08-08T13:27:00-07:00
author = "Owen"
tags = [ "work", "Ubuntu", "linux", "shell",]
+++
Ubuntu community help forum has [a nice
page](https://help.ubuntu.com/community/FindingFiles) if you need to be
reminded how to search files provided by a particular package.  
  
dpkg -L will show you what files came with an installed package  
  
apt-file, which needs to be installed first, will tell you what package
provides a given file.  Actually, it can also replicate the same thing
that dpkg -L does, see below:  

    $ dpkg -L picard-tools
    /.
    /usr
    /usr/bin
    /usr/bin/picard-tools
    /usr/share
    /usr/share/java
    /usr/share/java/picard-1.27.jar
    /usr/share/picard-tools
    /usr/share/picard-tools/explain_sam_flags.py
    /usr/share/doc
    /usr/share/doc/picard-tools
    /usr/share/doc/picard-tools/copyright
    /usr/share/doc/picard-tools/README.Debian
    /usr/share/man
    /usr/share/man/man1
    /usr/share/man/man1/picard-tools.1.gz
    /usr/share/java/picard.jar

    $ apt-file search picard.jar
    picard-tools: /usr/share/java/picard.jar

    $ apt-file list picard-tools
    picard-tools: /usr/bin/picard-tools
    picard-tools: /usr/share/doc/picard-tools/README.Debian
    picard-tools: /usr/share/doc/picard-tools/copyright
    picard-tools: /usr/share/java/picard-1.27.jar
    picard-tools: /usr/share/java/picard.jar
    picard-tools: /usr/share/man/man1/picard-tools.1.gz
    picard-tools: /usr/share/picard-tools/explain_sam_flags.py


    Addendum:  If you need to know what repository provides a specific package, use apt-cache showpkg:
    $ apt-cache showpkg picard-tools
    Package: picard-tools
    Versions: 
    1.27-1 (/var/lib/apt/lists/us.archive.ubuntu.com_ubuntu_dists_natty_universe_binary-amd64_Packages) (/var/lib/dpkg/status)
     Description Language: 
                     File: /var/lib/apt/lists/us.archive.ubuntu.com_ubuntu_dists_natty_universe_binary-amd64_Packages
                      MD5: 5ece67d6a9fa35d5b4adc3567de3557b


    Reverse Depends: 
      med-bio,picard-tools
      libsam-java,picard-tools
    Dependencies: 
    1.27-1 - openjdk-6-jre (16 (null)) java-runtime (0 (null)) libsam-java (2 1.27-1) python (0 (null)) r-base-core (0 (null)) 
    Provides: 
    1.27-1 - 
    Reverse Provides:
