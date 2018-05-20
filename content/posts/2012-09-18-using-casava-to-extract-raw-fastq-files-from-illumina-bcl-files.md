+++
title = "Using CASAVA to extract raw fastq files from Illumina BCL files"
slug = "2012-09-18-using-casava-to-extract-raw-fastq-files-from-illumina-bcl-files"
published = 2012-09-18T13:51:00-07:00
author = "Owen"
tags = []
+++
Here is how you can extract raw fastq files from Illumina BCL data.  
  
This will give you raw fastq files.  No demultiplexing.  Just the reads,
and nothin' but the reads.  
  
Read 1 is generally the forward read, Read 2 is generally the index
read, and Read 3 is generally the reverse read.  
  
You might want to do this if you want to see the barcode read quality
scores, which you may want to consider to do a more accurate
demultiplexing.  Examining these quality scores may also help you
understand "barcode bleed" (aka, Illumina's dirty little secret.)  
  
Here is what I did:  
  
1) get a copy of CASAVA 1.8.  Illumina technical support can hook you
up.  I'm using CASAVA-1.8.2.  \[edit: seems you can download it from
[here](http://support.illumina.com/sequencing/sequencing_software/casava.ilmn).\]  
  
2) Get the entire run directory, which should look something like this
(this is from MiSeq data):  
  
<span
style="font-family: Courier New, Courier, monospace;">120822\_M00609\_0035\_A000000000-A1CDK</span>  
<span style="font-family: Courier New, Courier, monospace;">|--
Config</span>  
<span style="font-family: Courier New, Courier, monospace;">|--
Data</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |--
Intensities</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |--
BaseCalls</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|-- L001</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|   |-- C1.1   \#</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|   |-- C10.1  \# the BCL files live here</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|   |-- C100.1 \# (one per cycle per tile)</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|   |-- and so on</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|-- Matrix</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
\`-- Phasing</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |--
L001</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|-- C1.1       \#</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|-- C10.1      \# the FWHMMap files live here</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|-- C100.1     \# (one per cycle per tile per base)</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   |  
|-- and so on</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |   \`--
Offsets</span>  
<span style="font-family: Courier New, Courier, monospace;">|   |--
RTALogs</span>  
<span style="font-family: Courier New, Courier, monospace;">|   \`--
TileStatus</span>  
<span style="font-family: Courier New, Courier, monospace;">|--
Images</span>  
<span style="font-family: Courier New, Courier, monospace;">|   \`--
Focus</span>  
<span style="font-family: Courier New, Courier, monospace;">|       \`--
L001</span>  
<span style="font-family: Courier New, Courier, monospace;">|          
|-- C1.1       \#</span>  
<span style="font-family: Courier New, Courier, monospace;">|          
|-- C10.1      \# the TIF images live here</span>  
<span style="font-family: Courier New, Courier, monospace;">|          
|-- C100.1     \# (one per cycle per tile)</span>  
<span style="font-family: Courier New, Courier, monospace;">|          
|-- and so on</span>  
<span style="font-family: Courier New, Courier, monospace;">|--
InterOp</span>  
<span style="font-family: Courier New, Courier, monospace;">|--
Logs</span>  
<span style="font-family: Courier New, Courier, monospace;">|--
Recipe</span>  
<span style="font-family: Courier New, Courier, monospace;">\`--
Thumbnail\_Images</span>  
<span style="font-family: Courier New, Courier, monospace;">    \`--
L001</span>  
<span style="font-family: Courier New, Courier, monospace;">        |--
C1.1</span>  
<span style="font-family: Courier New, Courier, monospace;">        |--
C10.1</span>  
<span style="font-family: Courier New, Courier, monospace;">        |--
C100.1</span>  
  
<span style="font-family: Courier New, Courier, monospace;">        |--
and so on</span>  

<span style="font-family: Courier New, Courier, monospace;">  
</span>

<span style="font-family: Courier New, Courier, monospace;">1250
directories</span>  

  
3) Delete the SampleSheet.csv file -- really!  In my experience, and for
my purposes, I just want to get the raw fastq files.  I would actually
prefer it if the standard Illumina pipeline ALWAYS produced an
unprocessed, undemultiplexed FASTQ file for each read (R1 and the index
read if single end, or R1, R2, and the index read if paired end).  I
find the SampleSheet to be fussy, often this data is not available to me
when I am trying to extract the sequences, and anyway, I would like to
see empirically what barcodes are present in the raw reads.  So that is
why I recommend doing this without a SampleSheet file.  
  

3) Run the configureBclToFastq.pl script to generate the make file (this
is fast).  There are two tricks to getting this to work:  you must
provide the Data/Intensities/BaseCalls directory, and you have to give
it a "bases-mask".  The bases mask defines which cycles gets assigned to
which reads.  The "y" in "y151" means, "Yes, I want the first 151
cycle", then "Yes, I wan the next 6 cyles", and "Yes, I want the next
151 cycles".  I think the standard way to run casava would be
"y151,<span style="background-color: yellow;">I</span>6,y151" which
renders the index read to the casava demultiplexing pipeline (in other
words, you don't actually get to see the index reads).  
  
  
<span style="font-family: Courier New, Courier, monospace;">$
configureBclToFastq.pl --input-dir
120822\_M00609\_0035\_A000000000-A1CDK/Data/Intensities/BaseCalls/
--output-dir fastq --force --use-bases-mask y151,y6,y151</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:24\]   \[configureBclToFastq.pl\]        INFO: Creating directory
'/home/username/fastq'</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:25\]   \[configureBclToFastq.pl\]        INFO: Basecalling
software: RTA</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:25\]   \[configureBclToFastq.pl\]        INFO:            
 version: 1.14 (build 23)</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:25\]   \[configureBclToFastq.pl\]        INFO: Original use-bases
mask: y151,y6,y151</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:25\]   \[configureBclToFastq.pl\]        INFO: Guessed use-bases
mask:
yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy,yyyyyy,yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy</span>  
<span style="font-family: Courier New, Courier, monospace;">Creating
directory
'/home/username/fastq/Project\_000000000-A1CDK/Sample\_lane1'</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:25\]   \[configureBclToFastq.pl\]        INFO: Read 1: length =
151: mask =
yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:25\]   \[configureBclToFastq.pl\]        INFO: Read 2: length = 6:
mask = yyyyyy</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:25\]   \[configureBclToFastq.pl\]        INFO: Read 3: length =
151: mask =
yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:26\]   \[configureBclToFastq.pl\]        INFO: Running self tests:
'make self\_test'</span>  
<span style="font-family: Courier New, Courier, monospace;">\[2012-09-18
12:06:27\]   \[configureBclToFastq.pl\]        INFO: Running self tests
on /home/username/fastq completed with no problems</span>  
  
Note that there is something about adding one cycle to the expected
number of bases, when working with MiSeq data.  It has something to do
with the way the cycles are reported back from the machine.  Basically,
it means that if you are expecting 150 bp reads, you need to put in
"y151".  Illumina can help you understand this, maybe.  Give them a
call.  
  
  
4) Go to the newly create fastq directory and type make (this is
slow).  
  
<span style="font-family: Courier New, Courier, monospace;">cd
fastq</span>  
<span
style="font-family: Courier New, Courier, monospace;">make</span>  
  
5) Your new fastq files should be in the "Project" directory (in my
case, "Project\_000000000-A1CDK"):  
  
  
<span style="font-family: Courier New, Courier, monospace;">$ ls -l
Project\_000000000-A1CDK/Sample\_lane1/</span>  
<span style="font-family: Courier New, Courier, monospace;">total
1523748</span>  
<span style="font-family: Courier New, Courier, monospace;">-rw-rw-r-- 1
username username 427960158 Sep 18 12:08
lane1\_NoIndex\_L001\_R1\_001.fastq.gz</span>  
<span style="font-family: Courier New, Courier, monospace;">-rw-rw-r--
1 username username 342223846 Sep 18 12:09
lane1\_NoIndex\_L001\_R1\_002.fastq.gz</span>  
<span style="font-family: Courier New, Courier, monospace;">-rw-rw-r--
1 username username  44789925 Sep 18 12:09
lane1\_NoIndex\_L001\_R2\_001.fastq.gz</span>  
<span style="font-family: Courier New, Courier, monospace;">-rw-rw-r--
1 username username  35997119 Sep 18 12:10
lane1\_NoIndex\_L001\_R2\_002.fastq.gz</span>  
<span style="font-family: Courier New, Courier, monospace;">-rw-rw-r--
1 username username 392045984 Sep 18 12:11
lane1\_NoIndex\_L001\_R3\_001.fastq.gz</span>  
<span style="font-family: Courier New, Courier, monospace;">-rw-rw-r--
1 username username 315694744 Sep 18 12:12
lane1\_NoIndex\_L001\_R3\_002.fastq.gz</span>  
  
6) To demultiplex fastq files with a separate fastq file for the barcode
read, refer to my recent post:  [How to demultiplex fastq files with a
dedicated, separate barcode
file](http://biocozy.blogspot.com/2012/10/how-to-demultiplex-fastq-files-with.html).
