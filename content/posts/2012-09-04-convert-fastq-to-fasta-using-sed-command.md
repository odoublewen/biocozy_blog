+++
title = "Convert FASTQ to FASTA using sed command"
slug = "2012-09-04-convert-fastq-to-fasta-using-sed-command"
published = 2012-09-04T15:44:00.003000-07:00
author = "Owen"
tags = []
+++
Easiest possible solution, and I believe significantly faster than
awk-based methods:

  

    sed -n '1~4s/^@/>/p;2~4p' 

  
  
The only assumption made is that each read occupies exactly 4 lines in
the FASTQ file, but that seems pretty safe, in my experience.  

  

If you find this helpful, go up-vote my [answer in
StackOverflow](http://stackoverflow.com/a/10359425/310441).
