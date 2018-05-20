+++
title = "GNU parallel -- the best thing since sliced bread"
slug = "2012-03-27-gnu-parallel-the-best-thing-since-sliced-bread"
published = 2012-03-27T08:38:00-07:00
author = "Owen"
tags = []
+++
[![](../images/thumbnails/2012-03-27-gnu-parallel-the-best-thing-since-sliced-bread-logo-gray+black300.png)](../images/2012-03-27-gnu-parallel-the-best-thing-since-sliced-bread-logo-gray+black300.png)When
I first found [GNU parallel](http://www.gnu.org/software/parallel/) last
fall, I thought it was the bee's knees. So well conceived, so well
executed, so well documented... so **generous** to the user, and most of
all, so darn handy.  
  
  
I've been using it extensively with the ::: notation to feed data files
into a pipeline in parallel, and it does exactly what I want it to do.  
  
But today it goes to a whole new level, as I realize there is a whole
other side to the tool: the ability to feed **parts** of a single input
file into a pipeline in parallel.  
  
For example, [BLAST](http://www.ncbi.nlm.nih.gov/books/NBK7152/) can be
effectively (embarrassingly) parallelized as follows:  

    cat temp.fa | parallel -j 10 --block 100k --recstart '>' --pipe blastn -evalue 0.01 -outfmt 6 -db refseq_genomic -query - > result.txt

  
The magic is in the **pipe** option.  Of course, we've all written blast
parallelizers, but I've never seen a solution as neat and simple as this
one liner!  
  
This is from [Michael Kuhn's excellent
post](http://blog.mckuhn.de/2012/01/embarrassingly-parallel-blast-search.html)
on the subject.  Thanks!
