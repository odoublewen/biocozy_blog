+++
title = "How to demultiplex fastq files with a dedicated, separate barcode file"
slug = "2012-10-16-how-to-demultiplex-fastq-files-with-a-dedicated-separate-barcode-file"
published = 2012-10-16T12:12:00.003000-07:00
author = "Owen"
tags = []
+++
Oh, Barcodes, How do I obtain thee?  Let me count the ways:  
1) Internal to one of the reads  
2) Printed in the header:  
3) Encoded in the header  
4) In a separate file  
  
There are many tools out there to deal with multiplexed read data.  
[fastx\_barcode\_splitter.pl](http://hannonlab.cshl.edu/fastx_toolkit/commandline.html#fastx_barcode_splitter_usage)(from
FASTX\_Toolkit)  
[fastq-multx](http://code.google.com/p/ea-utils/wiki/FastqMultx) (from
ea-utils)  
[split\_libraries\_fastq.py](http://qiime.org/scripts/split_libraries_fastq.html)
(from QIIME)  
  
As far as I know, none of the above adequately deal with case (4) above.
 The QIIME tools does, but appears to turn the fastq into a fasta file
in the process (?).  
  
Here is a one-liner homebrew solution to this situation:  just tack the
index reads onto the front of read1, and then use an off-the-shelf tool
(I like the FASTX\_Toolkit one above) to demultiplex.  Like this:  
  
paste -d '' &lt;(echo; sed -n '1,${n;p;}' <span
style="background-color: yellow;">R2.fq</span> | sed G) <span
style="background-color: lime;">R1.fq</span> | sed '/^$/d' |
fastx\_barcode\_splitter.pl --bol --bcfile <span
style="background-color: #cfe2f3;">barcodes.txt</span> --prefix
debarcoded  

  

I am assuming that <span
style="background-color: yellow;">R2.fq</span> is the barcode fastq
file, and <span style="background-color: lime;">R1.fq</span> is the is
the Read 1 file.  The commands above take the 2nd and 4th lines from the
barcode fastq file, spaces them out correctly, pastes them together
(with no delimiter - note: '' is a double single-quote, not a single
double-quote), and then uses another paste command to pre-pend THAT
result to the R1 file.  Also there is a final sed command to remove the
trailing blank lines.  It ain't pretty, but it works.  
  
The fancy &lt;(  ) constructs is a bash thing called "[process
substitution](http://tldp.org/LDP/abs/html/process-sub.html)".  If
you're not using bash, it won't work.  
  
Hope this helps someone.  
  
(edit:  I simplified the initial sed command on 2/1/2013, so let me know
if it somehow broke, but it should still work fine.)
