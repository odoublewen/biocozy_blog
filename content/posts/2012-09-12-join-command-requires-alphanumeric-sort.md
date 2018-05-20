+++
title = "join command requires alphanumeric sort"
slug = "2012-09-12-join-command-requires-alphanumeric-sort"
published = 2012-09-12T12:02:00-07:00
author = "Owen"
tags = [ "linux", "shell",]
+++
You may already know that the linux join command requires sorted fields
to work properly -- after all, it tells you so right in the man page:  
  
<span style="font-family: Courier New, Courier, monospace;">Important:
FILE1 and FILE2 must be sorted on the join fields.</span>

  
But I just found out the hard way that it must be an **alphanumeric**
sort, not a numeric sort.  
  
Lesson learned.
