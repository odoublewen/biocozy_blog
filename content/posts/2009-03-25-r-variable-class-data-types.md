+++
title = "R variable class (data types)"
slug = "2009-03-25-r-variable-class-data-types"
published = 2009-03-25T14:06:00-07:00
author = "Owen"
tags = [ "r-project",]
+++
R does some amazing things, and often seems to know just want you want
to do. Data type "coercion" can also backfire.  
  
I just discovered a great way to check to see how R has interpreted the
columns of a file you have just loaded.  
  
<span style="font-family: courier new;">&gt; sapply(dataframeobject,
class)</span>  
<span style="font-family: courier new;"> gender type score</span>  
<span style="font-family: courier new;">"factor" "factor"
"numeric"</span>
