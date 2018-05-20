+++
title = "Integrating BioMart queries into BioConductor with the biomaRt package"
slug = "2009-03-25-integrating-biomart-queries-into-bioconductor-with-the-biomart-package"
published = 2009-03-25T10:33:00-07:00
author = "Owen"
tags = [ "r-project", "data mining", "annotation",]
+++
I've just realized the considerable power and convenience of a web-based
bioinformatic resource I have overlooked in the past: biomart.org.  
  
What gets my attention now is the ability to integrate BioMart queries
right into your BioConductor pipeline, with a package called biomaRt  
  
The [Seattle 2009 BioConductor
workshop](http://www.bioconductor.org/workshops/2009/SeattleJan09/)
looks like it was great -- sadly, I missed it. But you can still access
some [presentation materials on
biomaRt](http://www.bioconductor.org/workshops/2009/SeattleJan09/biomaRt/).  
  
Installation of biomaRt is accomplished like any other BioConductor
pacakge:  
  

        source("http://bioconductor.org/biocLite.R")
      biocLite("biomaRt")

I am looking forward to learning more about these resources.
