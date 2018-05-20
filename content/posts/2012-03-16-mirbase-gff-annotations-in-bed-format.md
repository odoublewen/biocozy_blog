+++
title = "mirbase gff annotations in bed format"
slug = "2012-03-16-mirbase-gff-annotations-in-bed-format"
published = 2012-03-16T03:11:00-07:00
author = "Owen"
tags = [ "bioinformatics",]
+++
The [mirbase.org](http://mirbase.org/) folks in Manchester are doing a
great job, I think, but they only
[release](http://mirbase.org/ftp.shtml) their annotations in gff format.
 I think the following will convert that into an acceptable
[bed-format](http://genome.ucsc.edu/FAQ/FAQformat#format1) file:  

    ## get mirbase18 annotation and convert to a bed like format
     wget ftp://mirbase.org/pub/mirbase/CURRENT/genomes/hsa.gff
     grep -v "#" hsa.gff | cut -f 1,4,5,9 >mirbase18.temp1
     grep -v "#" hsa.gff | cut -f 6,7 >mirbase18.temp2
     paste mirbase18.temp1 mirbase18.temp2 | sed s/^/chr/ >mirbase18.bed

  
Extra credit: Is there a clever shell trick to piping two separate
stdins into paste, thus avoiding the temp files?
