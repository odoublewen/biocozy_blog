+++
title = "Bowtie2 Version 2.2.0 released -- HUGE news!"
slug = "2014-02-12-bowtie2-version-2-2-0-released-huge-news"
published = 2014-02-12T15:13:00.004000-08:00
author = "Owen"
tags = []
+++
How big is this news?  Well, bigger than 4 GB, that's for sure.

  

A while back I [brought up this issue on
BioStars](http://www.biostars.org/p/52742/).

  
From the [Bowtie2 news
page](http://bowtie-bio.sourceforge.net/bowtie2/news.shtml):  

Version 2.2.0 - February 10, 2014
---------------------------------

-   Improved index querying efficiency using "population count"
    instructions available since
    [SSE4.2](http://en.wikipedia.org/wiki/SSE4.2#SSE4.2)
-   <span style="background-color: yellow;">Added support for large and
    small indexes, removing 4-billion-nucleotide barrier. **Bowtie 2 can
    now be used with reference genomes of any size**</span>**.**
-   Fixed bug that could cause bowtie2-build to crash when reference
    length is close to 4 billion.
-   Added a `CL:` string to the `@PG` SAM header to preserve information
    about the aligner binary and paramteres.
-   Fixed bug that could cause `bowtie2-build` to crash when reference
    length is close to 4 billion.
-   No longer releasing 32-bit binaries. Simplified manual and Makefile
    accordingly.
-   Credits to the Intel® enabling team for performance optimizations
    included in this release. Thank you!
-   Phased out CygWin support. MinGW can still be used for Windows
    building.
-   Added the .bat generation for Windows.
-   Fixed some issues with some uncommon chars in fasta files.
-   Fixed wrappers so bowtie can now be used with symlinks.
