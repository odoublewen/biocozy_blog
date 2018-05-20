+++
title = "Getting yum to work with RHEL / RHN behind a proxy"
slug = "2013-04-09-getting-yum-to-work-with-rhel-rhn-behind-a-proxy"
published = 2013-04-09T13:19:00.001000-07:00
author = "Owen"
tags = []
+++
/etc/sysconfig/rhn/up2date

  

<span
style="font-family: Courier New, Courier, monospace;">enableProxy=0</span>

<span
style="font-family: Courier New, Courier, monospace;">httpProxy=proxyserver.company.com:8080</span>

  

  

~/.bash\_profile

  

<span style="font-family: Courier New, Courier, monospace;">export
http\_proxy=http://proxyserver.company.com:8080</span>

<span style="font-family: Courier New, Courier, monospace;">export
HTTP\_PROXY=http://proxyserver.company.com:8080</span>

  

  

The thing is, there is no universal agreement among linux command line
programs, some seem to use HTTP\_PROXY and some use http\_proxy.  So,
yes, export http\_proxy both as lower and UPPER case!

  

And complicating the picture is that RHN doesn't use either of these --
it pulls the settings out of /etc/sysconfig/rhn/up2date
