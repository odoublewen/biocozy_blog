+++
title = "Setting up JBrowse 1.8.1 on a CentOS 5.8"
slug = "2013-02-27-setting-up-jbrowse-1-8-1-on-a-centos-5-8"
published = 2013-02-27T11:06:00.002000-08:00
author = "Owen"
tags = []
+++
Some important details to successfully set up
[JBrowse](http://jbrowse.org/install/) on a Centos 5.8 machine.

  

Install and compile samtools from source.  I built it with fPIC flags
like this:  
  
<span style="font-family: Courier New, Courier, monospace;">make
CXXFLAGS=-fPIC CFLAGS=-fPIC CPPFLAGS=-fPIC</span>  
  
Be sure that the file libbam.a that you just created with the fPIC flag
is (also) present in the lib directory.  I had to rename the old one and
copy the new one there.  
  
  
<span style="font-family: Courier New, Courier, monospace;">\# ls -al
/usr/local/samtools/lib\*</span>  
<span style="font-family: Courier New, Courier, monospace;">-rw-rw-r-- 1
odsolbe odsolbe 309986 Feb 27 09:51
/usr/local/samtools/libbam.a</span>  
<span style="font-family: Courier New, Courier, monospace;">  
</span><span
style="font-family: Courier New, Courier, monospace;">/usr/local/samtools/lib:</span>  
<span style="font-family: Courier New, Courier, monospace;">total
1316</span>  
<span style="font-family: Courier New, Courier, monospace;">drwxr-xr-x 2
odsolbe odsolbe    4096 Feb 27 09:54 .</span>  
<span style="font-family: Courier New, Courier, monospace;">drwxr-xr-x 7
odsolbe odsolbe    4096 Feb 27 09:51 ..</span>  
<span style="font-family: Courier New, Courier, monospace;">-rw-rw-r-- 1
odsolbe odsolbe  309986 Feb 27 09:54 libbam.a</span>  
<span style="font-family: Courier New, Courier, monospace;">-rw-r--r-- 1
odsolbe odsolbe 1000346 Oct 24  2011 libbam.a\_orig</span>  

  

  
Set two env variables: <span style="white-space: pre-wrap;">SAMTOOLS and
PARL5LIB ([see
here](http://cpansearch.perl.org/src/LDS/Bio-SamTools-1.27/README))</span>  

<span style="white-space: pre-wrap;">  
</span><span
style="font-family: Courier New, Courier, monospace; white-space: pre-wrap;">export
PERL5LIB=/path/to/...../jbrowse/extlib/lib/perl5 export
SAMTOOLS=/usr/local/samtools</span>  
  
This is what worked for me.  Your milage may vary.
