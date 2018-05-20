+++
title = "Multiple lattice plots"
slug = "2009-08-05-multiple-lattice-plots"
published = 2009-08-05T16:27:00-07:00
author = "Mike"
tags = []
+++
Here's Owen's trick for displaying multiple lattice dotplots:  
  
In the reshape package, the function melt() allows you to reshape data
into variable/value columns, on one or more "id" column(s):  
  
`> library(reshape)> library(lattice)> d <- data.frame(a=rnorm(10), b=rnorm(10), c=rnorm(10), cond=factor(sample(1:2,10,replace=TRUE)))> d             a           b          c cond1   0.06927895  0.98947264  1.7256042    22  -2.02604891 -0.33003778 -0.6595201    13   0.38082836 -0.98114426  1.5448757    24  -2.73939190 -1.30930261  0.1118557    15   0.37405184 -0.45263384  1.0484490    16  -0.68747094 -0.78446749  0.3484745    27   0.13011011  1.01275070 -0.5005770    18  -0.33158390  1.38201954  0.3096848    19   0.07920194  0.05604219 -1.8579733    210 -0.49055146 -1.17780285  0.6850589    1> melt(d, id="cond")   cond variable       value1     2        a  0.069278952     1        a -2.026048913     2        a  0.380828364     1        a -2.739391905     1        a  0.374051846     2        a -0.687470947     1        a  0.130110118     1        a -0.331583909     2        a  0.0792019410    1        a -0.4905514611    2        b  0.9894726412    1        b -0.3300377813    2        b -0.9811442614    1        b -1.3093026115    1        b -0.4526338416    2        b -0.7844674917    1        b  1.0127507018    1        b  1.3820195419    2        b  0.0560421920    1        b -1.1778028521    2        c  1.7256042522    1        c -0.6595201523    2        c  1.5448756624    1        c  0.1118557325    1        c  1.0484489526    2        c  0.3484745227    1        c -0.5005769928    1        c  0.3096847629    2        c -1.8579733130    1        c  0.68505890> stripplot(value~cond|variable,melt(d, id="cond"),scales=list(relation="free"))`  
  
Setting parameter as.table=TRUE will plot from top left to bottom
right.  
  
[![](../images/thumbnails/2009-08-05-multiple-lattice-plots-lattice.example.png)](../images/2009-08-05-multiple-lattice-plots-lattice.example.png)
