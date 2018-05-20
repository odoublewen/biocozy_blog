+++
title = "parallel computation using the caret package"
slug = "2009-10-05-parallel-computation-using-the-caret-package"
published = 2009-10-05T13:56:00.001000-07:00
author = "Owen"
tags = [ "r-project", "Bioconductor", "parallel computing",]
+++
Library <span
style="font-weight: bold;font-family:courier new;">caret</span> is a
wonderful R package for tuning a variety of machine learning
classification and regression algorithms. But it can take a long time to
run, since model tuning usually involves running multiple bootstrapped
replicates for each point in your tuning grid.  
  
If you have a multi-core desktop machine, you can speed up your calls to
the caret function <span style="font-weight: bold;">train</span> by
using explicit parallelism.  
  
There were just a couple hitches to get it flying on my 64bit quad core
Optiplex 960 running linux kernel 2.6.28-15 x86\_64, and R version 2.9.2
(2009-08-24). I present these hitches here in hopes of saving you
time.  
  
First, use apt-get to install some necessary dependencies:  
  
<span style="font-weight: bold;font-family:courier new;">sudo apt-get
install lam4-dev lam-runtime libopenmpi1 openmpi-common</span>  
  
Then sudo into R, and use the install.packages() function to install
snow and Rmpi. (Do not install Rmpi using apt or synaptic. In general,
it is always a better idea to get R packages directly from CRAN using
the built-in function.)  
  
&gt; install.packages("Rmpi")  
&gt; install.packages("snow")  
  
Anyway, after you have all of the above install, just follow the
framework shown in the manual for train:  
  
mpiClacs &lt;- function(X, FUN, ...) {  
theDots &lt;- list(...)  
parLapply(theDots$cl, X, FUN)  
}  
  
cl &lt;- makeCluster(4, "MPI") \#\#\#\#\# I am using 4 b/c I have a quad
core processor  
  
\#\# This is how we inform "train" that we will have multiple processors
available  
mpiControl &lt;- trainControl(workers = 4,  
number = 25,  
computeFunction = mpiClacs,  
computeArgs = list(cl = cl))  
  
set.seed(1)  
  
tune &lt;- train(method="rf", x = t(exprs(es)), y = es$dx, ntree =
10000,  
tuneGrid=data.frame(.mtry=c(3:7)\*200),  
trControl = mpiControl)  
  
  
  
stopCluster(cl)  
  
  
  
Hope this helps!
