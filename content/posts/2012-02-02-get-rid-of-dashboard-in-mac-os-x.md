+++
title = "get rid of dashboard in mac os X"
slug = "2012-02-02-get-rid-of-dashboard-in-mac-os-x"
published = 2012-02-02T02:50:00-08:00
author = "Owen"
tags = [ "Mac OS X", "computers",]
+++
Dashboard seems like a good idea, but I can't stand how it always seems
to take 5 seconds to "wake up" all those widgets whenever I open it up.
So, as a result, I never use it.  It just idles there in the background
taking up a sliver of CPU cycles. Oh and occasionally I accidentally key
into it. So, I am glad I finally did
[this](http://www.macworld.com/article/46236/2005/08/disabledashboard.html):  
  
`defaults write com.apple.dashboard mcx-disabled -boolean YES`  
  
`killall Dock`  
  
``
