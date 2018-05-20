+++
title = "How to use the sqlite connection to AnnotationDbi packages"
slug = "2009-09-17-how-to-use-the-sqlite-connection-to-annotationdbi-packages"
published = 2009-09-17T13:09:00-07:00
author = "Owen"
tags = []
+++
It is very fast and very straightforward:  
  
<span style="font-family: courier new;">library(hgu133plus2.db)</span>  
<span style="font-family: courier new;">hgu133plus2\_dbschema()</span>  
  
<span style="font-family: courier new;">sql = "</span>  
<span style="font-family: courier new;">select \* from probes p,
gene\_info g, chromosome\_locations c </span>  
<span style="font-family: courier new;">where g.\_id=c.\_id and
g.\_id=p.\_id limit 10</span>  
<span style="font-family: courier new;">"</span>  
  
<span
style="font-family: courier new;">dbGetQuery(hgu133plus2\_dbconn(),
sql)</span>  
  
  
If you look at the last few page of the manual for AnnotationDbi
\[[site](http://www.bioconductor.org/packages/release/bioc/html/AnnotationDbi.html),
[PDF](http://www.bioconductor.org/packages/release/bioc/vignettes/AnnotationDbi/inst/doc/AnnotationDbi.pdf)\],
you will see some tips about joining different databases together.
