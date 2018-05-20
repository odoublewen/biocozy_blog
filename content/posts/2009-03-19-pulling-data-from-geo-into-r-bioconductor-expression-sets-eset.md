+++
title = "Pulling data from GEO into R Bioconductor expression sets (eSet)"
slug = "2009-03-19-pulling-data-from-geo-into-r-bioconductor-expression-sets-eset"
published = 2009-03-19T16:01:00-07:00
author = "Owen"
tags = [ "r-project", "GEO", "Bioconductor",]
+++
I just discovered how easy Bioconductor makes it to import data from the
Gene Expression Omnibus (GEO).  
  
First, be sure you have the GEOquery package from Bioconductor. You will
probably need to install the curl4 devel library package using apt-get
or whatever you use to do such things. On my Ubuntu 8.10 distro, the
requisite package is called libcurl4-gnutls-dev. After you have this,
you should be able to install GEOquery like any other Bioconductor
package, ie:  
  
<span
style="font-family:courier new;">source("http://bioconductor.org/biocLite.R")</span>  
<span style="font-family:courier new;">biocLite("GEOquery")</span>  
  
Then, pulling a GEO series (GSE) into an eSet object is as simple as:  
  
<span style="font-family:courier new;">gseObj &lt;-
getGEO("GSE10667")</span>  
<span style="font-family:courier new;">eSet &lt;-
gseObj\[\[1\]\]</span>  
  
Note the \[\[1\]\] -- necessary because the GSE comes in as a list of
eSets, apparently.  
  
See the [GEOquery
vignette](http://www.bioconductor.org/packages/2.2/bioc/html/GEOquery.html)
for more details, and for conversions from GDS format.
