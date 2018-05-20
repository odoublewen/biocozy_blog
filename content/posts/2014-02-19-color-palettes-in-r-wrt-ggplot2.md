+++
title = "Color palettes in R (wrt ggplot2)"
slug = "2014-02-19-color-palettes-in-r-wrt-ggplot2"
published = 2014-02-19T12:29:00.001000-08:00
author = "Owen"
tags = []
+++
I just found an [outstanding rundown of color
issues](http://www.cookbook-r.com/Graphs/Colors_%28ggplot2%29/) in R
(with a nod to ggplot2) on cookbook-r.com.  
  
Mostly just a collection of resources from around the web.  
  
I really like their colorblind friendly palette:  
  

[TEMPORARY](http://www.cookbook-r.com/Graphs/Colors_(ggplot2)/colorblind-gray.png)

     

    cbPalette <- span=""> c("#999999", "#E69F00", "#56B4E9", "#009E73", "#F0E442", "#0072B2", "#D55E00", "#CC79A7")

  
  
Which is better than the ggplot2 defaults:  

[TEMPORARY](http://www.cookbook-r.com/Graphs/Colors_(ggplot2)/ggplot2_scale_hue_colors.png)
