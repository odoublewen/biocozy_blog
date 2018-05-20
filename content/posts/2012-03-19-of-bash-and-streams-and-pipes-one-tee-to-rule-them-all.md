+++
title = "Of bash and streams and pipes - One Tee To Rule Them All"
slug = "2012-03-19-of-bash-and-streams-and-pipes-one-tee-to-rule-them-all"
published = 2012-03-19T05:17:00.001000-07:00
author = "Owen"
tags = []
+++
There is a [great answer](http://stackoverflow.com/a/60955/310441) on
stack overflow showing how to feed one output stream into multiple
processes.  It is a little bit of a hack of the excellent tool tee,
which I've been using for some time.  Normally, tee take stout and
writes it to a file, while passing it along to stout.  This solution
provided on s.o. shows how to hack this with the bash trick
&gt;(process)  -- so as far as tee knows, it is writing to 2 or more
files, but the "files" are actually background processes.

This syntax is bash-dependent, so won't work in sh, and this will likely
come up if you're using system() in, say,  perl.  There is
another [excellent answer](http://stackoverflow.com/a/571383/310441) on
stack overflow on how to deal with this.

Side note:  Using the &lt;(command) trick, my [post from March
16](http://arrayal.wordpress.com/2012/03/16/mirbase-gff-annotations-in-bed-format/) can
now be written:

    paste <(grep -v "#" hsa.gff | cut -f 1,4,5,9) <(grep -v "#" hsa.gff | cut -f 6,7) | sed s/^/chr/ >mirbase18.bed
