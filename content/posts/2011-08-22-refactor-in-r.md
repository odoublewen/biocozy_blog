+++
title = "refactor in R"
slug = "2011-08-22-refactor-in-r"
published = 2011-08-22T08:59:00-07:00
author = "Owen"
tags = [ "work", "R",]
+++
I use this little R function almost daily.  It just takes a factor,
drops the unused levels, and otherwise keeps the same ordering.  

    refactor <- function(x) {
      x <- factor(x, levels=levels(x)[levels(x) %in% x] )
      return(x)
    }

  
File this under "commands that should be included in R."
