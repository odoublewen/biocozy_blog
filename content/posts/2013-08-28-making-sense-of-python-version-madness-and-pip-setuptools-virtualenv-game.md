+++
title = "Making sense of Python version madness and pip/setuptools/virtualenv game"
slug = "2013-08-28-making-sense-of-python-version-madness-and-pip-setuptools-virtualenv-game"
published = 2013-08-28T07:02:00.001000-07:00
author = "Owen"
tags = []
+++
This posting is motivated by cases where you are stuck using an older
server OS (CentOS 5.8 in this case) and want to install an up-to-date
python 2.7 along with a raft of necessary packages.  What is the best
way?  
  
distribute? pip? setuptools? virtualenv?  What to make of all this?  
  
[Bottom
line](http://stackoverflow.com/questions/3220404/why-use-pip-over-easy-install):
use pip.  To install pip, you either install it from source, or else
install virtualenv (which includes pip).  Installing from source allows
you to manage packages with pip globally on your system (and not in a
virtual environment), then you have to install pip from source.  But to
install pip yourself, you first need to install setuptools.  All of
these installs should be done using the target python interpreter.   Got
that?  
  
I wrote the following notes after digesting the helpful hints given at a
variety of places, such
as [these](https://gist.github.com/stantonk/4082043) [two](https://gist.github.com/mersilde/1372355) gist
pages.  Note that although there are many tutorials that still guide you
to install virtualenv with easy\_install (such
as [here](http://simononsoftware.com/virtualenv-tutorial/) or [here](http://iamzed.com/2009/05/07/a-primer-on-virtualenv/)),
we're actually [not
supposed](http://stackoverflow.com/questions/4324558/whats-the-proper-way-to-install-pip-virtualenv-and-distribute-for-python)
to do it this way any longer.  My notes that follow will not make use of
virtualenv, but in some situations this might be desirable -- this is
just for a system-wide fresh installation of Python 2.7 and pip to
install packages. ([Here is a nice
overview](http://dubroy.com/blog/so-you-want-to-install-a-python-package/)
of setting up virtualenv if you want to go that route.)  
  
<span style="font-size: small;">First you want to be sure your CentOS
machine is ready to built something like Python:</span>  
  
<span
style="background-color: white; font-family: Consolas, 'Liberation Mono', Courier, monospace; font-size: 12px; line-height: 16px;">yum
groupinstall </span><span class="s2"
style="background-color: white; font-family: Consolas, 'Liberation Mono', Courier, monospace; font-size: 12px; line-height: 16px;">"Development
tools"</span>  

    yum install zlib-devel bzip2-devel openssl-devel ncurses-devel



    Then you will fetch and unzip Python:

    wget http://www.python.org/ftp/python/2.7.5/Python-2.7.5.tar.bz2
    tar xf Python-2.7.5.tar.bz2 

    cd Python-2.7.5
    Do the usual "configure, make, make install" waltz:  

     
    ./configure --prefix=/opt/python2.7.5 --with-threads --enable-shared
    makemake install

    At this point, it seems like you're done but not quite.  

$ /opt/python2.7.5/bin/python /opt/python2.7.5/bin/python: error while
loading shared libraries: libpython2.7.so.1.0: cannot open shared object
file: No such file or directory

    /opt/python2.7.5/
     

    The trick is to tell ldconfig where to find the new python shared libraries:  

<span class="nb" style="color: #0086b3;">echo</span> <span class="s2"
style="color: #dd1144;">"/opt/python2.7.5/lib/"</span> &gt;
/etc/ld.so.conf.d/opt-python2.7.5.conf

    ldconfig 

     

    Now we're cooking with gas: 

    $ /opt/python2.7.5/bin/python 

    Python 2.7.5 (default, Aug 21 2013, 09:50:18) 
    [GCC 4.1.2 20080704 (Red Hat 4.1.2-54)] on linux2

  
Get setuptools from the [setuptools project
page](https://pypi.python.org/pypi/setuptools).  You have to click on
the version you want and then to find the download link, scroll to the
very bottom of the page ("In the basement, down a long hallway behind a
door marked 'danger-TIGER!'")  
  
<span style="color: #b45f06;">Aside: I am having bad luck these days
trying to wget from https servers -- something about SSL certificates
and my corporate proxy and the old version of wget that is on CentOS
5.8.</span>  
<span style="color: #b45f06;">  
</span><span style="font-size: x-small;"><span
style="color: #b45f06; font-family: &quot;Courier New&quot;,Courier,monospace;">\#
wget
"https://pypi.python.org/packages/source/s/setuptools/setuptools-1.0.tar.gz"  
--2013-08-21 11:49:47-- 
https://pypi.python.org/packages/source/s/setuptools/setuptools-1.0.tar.gz  
Resolving proxy.company.com... </span></span>  
<span style="font-size: x-small;"><span
style="color: #b45f06; font-family: &quot;Courier New&quot;,Courier,monospace;">Connecting
to proxy.company.com:8080... connected.  
ERROR: certificate common name \`\*.a.ssl.proxy.net' doesn't match
requested host name \`pypi.python.org'.  
To connect to pypi.python.org insecurely, use
\`--no-check-certificate'.  
Unable to establish SSL connection.</span></span>  
<span style="color: #b45f06;">  
</span><span style="color: #b45f06;">So curl seems to work better. 
Maybe because it is not checking SSL certs?</span>  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;"><span
style="color: #b45f06; font-size: x-small;">\# curl -O
"https://pypi.python.org/packages/source/s/setuptools/setuptools-1.0.tar.gz"  
  % Total    % Received % Xferd  Average Speed   Time    Time     Time 
Current  
                                 Dload  Upload   Total   Spent    Left 
Speed  
100  663k  100  663k    0     0   229k      0  0:00:02  0:00:02
--:--:--  359k</span></span>  
  
Once you have downloaded and untar'ed setuptools, you want to install
it.  But it seems the setuptools
[instructions](https://pypi.python.org/pypi/setuptools/1.0#installation-instructions)
appear flawed:  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;"><span
style="font-size: x-small;">\# /opt/python2.7.5/bin/python setup.py
--prefix=/opt/setuptools  
error: option --prefix not recognized</span></span>  
  
So just do the usual "python setup.py build and install" two-step.  Be
sure you are calling the desired target python version.  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;"><span
style="font-size: x-small;">/opt/python2.7.5/bin/python setup.py
build</span></span>  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;"><span
style="font-size: x-small;">/opt/python2.7.5/bin/python setup.py
install</span></span>  
  
Now you can install pip:  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;"><span
style="font-size: x-small;">curl -O
https://pypi.python.org/packages/source/p/pip/pip-1.4.1.tar.gz  
tar xvzf pip-1.4.1.tar.gz  
cd pip-1.4.1  
/opt/python2.7.5/bin/python setup.py build  
/opt/python2.7.5/bin/python setup.py install</span></span>  
And now... <span style="font-size: large;">now...</span> **<span
style="font-size: x-large;">NOW!</span>**  Praise the Almighty, you are
ready to use pip to install packages!!!  
  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;"><span
style="font-size: x-small;">/opt/python2.7.5/bin/pip install numpy   \#
install this before biopython</span></span>  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;"><span
style="font-size: x-small;">/opt/python2.7.5/bin/pip install
scipy</span></span>  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;"><span
style="font-size: x-small;">/opt/python2.7.5/bin/pip install
biopython</span></span>  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;"><span
style="font-size: x-small;">/opt/python2.7.5/bin/pip install
pysam</span></span>
