+++
title = "Mac function keys working with debian / ubuntu terminal and byobu"
slug = "2011-09-22-mac-function-keys-working-with-debian-ubuntu-terminal-and-byobu"
published = 2011-09-22T12:57:00-07:00
author = "Owen"
tags = []
+++
A minor irritation, but as I have begun running longer jobs, and getting
addicted to the excellent [byobu](https://launchpad.net/byobu)
adaptation of [GNU screen](http://www.gnu.org/s/screen/), I've been
frustrated that I can't access those easy function keys when I ssh in
from my Mac.  
  
I've pieced together a solution by reading
this [thread](https://bugs.launchpad.net/byobu/+bug/482623) and
this [excellent
resource](http://aperiodic.net/phil/archives/Geekery/term-function-keys.html).  
  
Here is what works for me, using OS X 10.6, with Terminal declaring
itself as "xterm-color":  in Terminal.app, go to preferences, and
replace the F1 thru F4 mappings to:  

    33[11~
    33[12~
    33[13~
    33[14~

  
EDIT:  Now I am using OS X 10.7, and my terminal is set to declare
"xterm-256color", and what works for me now is the following:  

    33OP
    33OQ
    33OR
    33OS

  
Where  33  is a &lt;ctrl&gt;\[
