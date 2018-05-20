+++
title = "How to get the BioConductor packages to install correctly in Ubuntu 8.10"
slug = "2008-12-15-how-to-get-the-bioconductor-packages-to-install-correctly-in-ubuntu-8-10"
published = 2008-12-15T11:15:00-08:00
author = "Owen"
tags = [ "r-project", "installation", "Ubuntu",]
+++
Apparently, the repositories for the 8.10 (Intrepid Ibex) release of
Ubuntu do not completely specify all of the dependencies for the R-base
synaptic package.  
  
I could not get various packages to compile, until I installed  
  
<span style="font-family:courier new;">sudo apt-get install libxml2-dev
</span><span class="fixed_width"
style="font-family:Courier,Monospaced;"><span
style="font-family:courier new;">libatlas-base-dev</span>  
  
</span>This solved many build problems, including package XML, but I was
still getting the following error when attempting to load library vsn:  
<span class="fixed_width"
style="font-family:Courier,Monospaced;"></span>

>   
> <span style="font-family:courier new;">&gt; library(vsn)</span>  
> <span style="font-family:courier new;">Loading required package:
> lattice</span>  
> <span style="font-family:courier new;">Loading required package:
> Biobase</span>  
> <span style="font-family:courier new;">Loading required package:
> tools</span>  
>   
> <span style="font-family:courier new;">Welcome to
> Bioconductor</span>  
>   
> <span style="font-family:courier new;"> Vignettes contain introductory
> material. To view, type</span>  
> <span style="font-family:courier new;"> 'openVignette()'. To cite
> Bioconductor, see</span>  
> <span style="font-family:courier new;"> 'citation("Biobase")' and for
> packages 'citation(pkgname)'.</span>  
>   
> <span style="font-family:courier new;">Loading required package:
> affy</span>  
> <span style="font-family:courier new;">Loading required package:
> affyio</span>  
> <span style="font-family:courier new;">Loading required package:
> preprocessCore</span>  
> <span style="font-family:courier new;">Loading required package:
> limma</span>  
> <span style="font-family:courier new;">Error in inherits(x, "factor")
> : attempt to apply non-function</span>  
> <span style="font-family:courier new;">Error : .onLoad failed in
> 'loadNamespace' for 'vsn'</span>  
> <span style="font-family:courier new;">Error: package/namespace load
> failed for 'vsn'</span>

  
Got it to work finally! I replaced the atlas lib mentioned above with
libatlas3gf-sse2 (specific for newer processors) and also updated all of
my bioconductor packages as follows:

    source("http://bioconductor.org/biocLite.R")
    update.packages(repos=biocinstallRepos(), ask=FALSE)

<span class="fixed_width" style="font-family:Courier,Monospaced;">  
</span>-----------  
references:  
<https://stat.ethz.ch/pipermail/r-help/2008-December/181390.html>  
<http://ubuntuforums.org/showthread.php?t=717069><span
class="fixed_width" style="font-family:Courier,Monospaced;">  
</span>
