+++
title = "Another workaround for Memory Issues in R / Bioconductor"
slug = "2009-04-15-another-workaround-for-memory-issues-in-r-bioconductor"
published = 2009-04-15T11:35:00-07:00
author = "Owen"
tags = [ "r-project", "workaround", "Bioconductor",]
+++
This post could be entitled "<span style="font-weight: bold;">Error:
cannot allocate vector of size 256.0 Mb</span>". R provides this
maddening response for even the most trivial seeming tasks. I have a 4
Gb linux system, and I have encountered this error message for "vector
of size" in the 10s of Mb. And system wide, there appears to be plenty
of memory still available, and the swap space hasn't been touched.  
  
What's going on with R memory management??  
  
There are many issues and many variables -- the overall amount of memory
in your system, whether you have a 32bit or 64bit systems, how much
memory is allocated to the R process (especially under windows), and of
course, the size of the "vector" that R is trying to allocate.  
  
But for me, the most salient topic is <span
style="font-weight: bold;">memory fragmentation</span>, aka the
swiss-cheese effect. Matthew Keller has an excellent discussion of the
topic [here](http://www.matthewckeller.com/html/memory.html), and I
won't try to go into all the details. But basically, even if you have
plenty of "free memory," you can run into this memory allocation error
if the "free" memory is discontinuous. The above link suggests some
workarounds, but here is one that I have not seen posted anywhere:  
  
<span style="font-weight: bold;">Quit R</span>. Yes, just quit! But
don't worry we will come back again!  
  
<span style="font-family: courier new;">&gt; q()</span>  
<span style="font-family: courier new;">Save workspace image? \[y/n/c\]:
y</span>  
  
Then, immediately start R again, and allow it to load in all the objects
you had before. I have been delighted to see that this actually gets me
around the vector allocation error. I guess what is happening, is that
the objects are all being read back in in a neatly packed manner, making
more continuous free memory.
