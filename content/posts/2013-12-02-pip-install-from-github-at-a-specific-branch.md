+++
title = "pip install from github at a specific branch"
slug = "2013-12-02-pip-install-from-github-at-a-specific-branch"
published = 2013-12-02T12:15:00.001000-08:00
author = "Owen"
tags = []
+++
I had difficulties figuring out how to use pip to install a specific
branch from a github repo.  Because of my corporate firewall, all of the
other methods that you can find around on various websites did not work
for me.  This is the method that worked:  
  
```
pip install
git+ssh://git@github.com/h3/django-dajaxice.git@django-1.5+  
```

Of course, I have `http_proxy` and `https_proxy` set and exported.
