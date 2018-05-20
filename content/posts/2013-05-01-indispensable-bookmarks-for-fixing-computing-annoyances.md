+++
title = "Indispensable bookmarks for fixing computing annoyances"
slug = "2013-05-01-indispensable-bookmarks-for-fixing-computing-annoyances"
published = 2013-05-01T09:08:00-07:00
author = "Owen"
tags = []
+++
This list will no doubt grow...  
  
[Understanding GNU Emacs and
Tabs](http://vserver1.cscs.lsa.umich.edu/~rlr/Misc/emacs_tabs.htm)  
Executive summary: put this in your .emacs.el file:  
  
<span
style="font-family: Courier New, Courier, monospace;">(setq-default
major-mode 'text-mode)</span>  
<span style="font-family: Courier New, Courier, monospace;">(define-key
text-mode-map (kbd "TAB") 'self-insert-command); </span>  

  

  
[ggplot2: Changing the Default Order of Legend Labels and Stacking of
Data](http://www.r-bloggers.com/ggplot2-changing-the-default-order-of-legend-labels-and-stacking-of-data/)  
Executive summary:  
  
<span
style="font-family: Courier New, Courier, monospace;">ggplot(diamonds,
aes(clarity, fill=cut, order= -as.numeric(cut))) </span>  
  
actually, this is better, [available in recent versions of
ggplot2](http://docs.ggplot2.org/current/guide_legend.html):  
<span style="font-family: Courier New, Courier, monospace;">guides(color
= guide\_legend(reverse = TRUE))</span>
