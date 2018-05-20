+++
title = "Amazed by RStudio!"
slug = "2012-10-23-amazed-by-rstudio"
published = 2012-10-23T12:02:00.002000-07:00
author = "Owen"
tags = []
+++
RStudio (<http://www.rstudio.com/>) has to be one of the coolest pieces
of software I have installed in recent memory.

  

RStudio provides a very well-planned and well-executed IDE for R.  This
alone would be a reason to sing Hosanna.

[TEMPORARY](http://www.rstudio.com/images/screenshots/rstudio-windows.png)

  

  

**But it gets better!!!**  The Server package (deb and rpm packages
available) allows you access to this same interface **via a webserver**,
so you can run R on a beefy computational server from any web browser.
 And it seems to work every bit as nicely as the locally installed IDE.

  

The user accounts are integrated with the linux user accounts, very
nice.  I even got it to work (after reading [this
post](http://support.rstudio.org/help/discussions/problems/1118-error-incorrect-or-invalid-usernamepassword))
in a kerberos situation by overwriting the "rstudio" pam file that the
RStudio package provides with the login one.  (You might want to back up
 the rstudio one first).

  

<span style="font-family: Courier New, Courier, monospace;">\# cd
/etc/pam.d/</span>

<span style="font-family: Courier New, Courier, monospace;">\# cp login
rstudio</span>

  

Well done and thank you to the [folks at the RStudio
company](http://www.rstudio.com/about/).
