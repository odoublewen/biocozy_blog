+++
title = "fork processes in R using package multicore"
slug = "2009-10-01-fork-processes-in-r-using-package-multicore"
published = 2009-10-01T16:17:00-07:00
author = "Owen"
tags = [ "parallel computing",]
+++
I just found this wicked cool way to fork processes (for multi-core
CPUs) in R.... Works just like you'd expect!  
  
library(multicore)  
  
job1 &lt;- mcparallel(bigMachingLeaningFunction1())  
job2 &lt;- mcparallel(bigMachingLeaningFunction2())  
job3 &lt;- mcparallel(bigMachingLeaningFunction3())  
job4 &lt;- mcparallel(bigMachingLeaningFunction4())  
  
\#\#\#\#\#\# time goes by .....  
  
results1 &lt;- collect(job1)  
results2 &lt;- collect(job2)  
results3 &lt;- collect(job3)  
results4 &lt;- collect(job4)  
  
  
Note to emacs ESS users -- just be sure all your libraries are already
loaded, and set silent=TRUE in the mcparallel call.... that will keep
your ESS buffer from going read-only.
