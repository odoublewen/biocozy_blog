+++
title = "Bio::SeqIO very very slow"
slug = "2011-08-04-bio-seqio-very-very-slow"
published = 2011-08-04T16:20:00-07:00
author = "Owen"
tags = [ "NGS", "work", "perl", "bioinformatics",]
+++
While it may be a convenient and flexible solution when reading in 10s
or 100s or 1000s of sequences, the SeqIO module of BioPerl is just not a
workable solution for reading in Next Gen Sequencing files.  
  
   
  
Consider reading in 100,000 short reads from a fastq file:  
  
It takes 30 seconds to do it the bioperl way:  
  
use Bio::SeqIO;  
my $seqin = Bio::SeqIO-&gt;new(-format =&gt; "fastq",-file   =&gt;
"infilename",);  
while( $seq = $seqin-&gt;next\_seq() ) { $seqhash{$seq-&gt;seq() } ++;
}  
  
   
  
But only 1/2 of a second to do it the home-made way (using basic file IO
module):  
  
use File::Util;  
my $f = File::Util-&gt;new();  
$ifh = $f-&gt;open\_handle('file' =&gt; $infilename, 'mode' =&gt;
'read');  
while(&lt;$ifh&gt;)  
{  
if($\_ =~ /\\@.\*/)  
{  
$counter++;  
$trigger = 1;  
}  
elsif($trigger == 1)  
{  
$\_ =~ /(\\w+)/;  
$seq = $1;  
$seqhash{$seq} ++;  
$trigger = 0;  
}  
}  
  
Not as elegant, but it works much faster!!
