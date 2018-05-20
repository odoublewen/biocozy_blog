+++
title = "Loading custom genomes into IGV"
slug = "2011-10-06-loading-custom-genomes-into-igv"
published = 2011-10-06T04:37:00-07:00
author = "Owen"
tags = []
+++
bp\_genbank2gff3  
  
bp\_genbank2gff3 -out stdout NC\_014117.gbk &gt;NC\_014117.gff3  
  
NC\_014117.gff3  
  
&gt;gi|295675101|ref|NC\_014117.1| Burkholderia sp. CCGE1002 chromosome
1, complete sequence  
AAAACCGCGCGATCATCGCTGAAAGCGCAATGGCCGGTGGTTTACTGGAATTGGTTTTCGCGGAACCCGC  
TATTTAAACCGGTTTTCCGTTGGCCGTCAATAGTTTAGCCCGCTTCTGACGCAGCCGACGTTTCCCGGGC  
  
NC\_014117.gff3  
  
\#\#gff-version 3  
\# sequence-region NC\_014117.1 1 3518940  
\# conversion-by bp\_genbank2gff3.pl  
\# organism Burkholderia sp. CCGE1002  
\# date 06-JUN-2011  
\# Note Burkholderia sp. CCGE1002 chromosome 1, complete sequence.  
NC\_014117.1 GenBank chromosome 1 3518940 . + .
ID=NC\_014117.1;Alias=1;Dbxref=taxon:640511  
NC\_014117.1 GenBank gene 363 1961 . + .
ID=BC1002\_0001;Dbxref=GeneID:9090916;locus\_tag=BC1002\_0001  
  
samtools view ALL\_NC\_014117.sorted.bam |head  
  
SOLEXA2\_0903\_FC628A5AAXX:8:82:19168:11203\#0/1 0
gi|295675101|ref|NC\_014117.1| 130 255 15M \* 0 0 GTTTCCCGGGCGATG
fffffeffffffdff XA:i:0 MD:Z:15 NM:i:0  
SOLEXA1\_0917\_FC628DCAAXX:2:46:13694:14478\#0/1 0
gi|295675101|ref|NC\_014117.1| 2620 255 15M \* 0 0 CGATTTCGGCGTCGG
ffaffffffffdfcf XA:i:0 MD:Z:15 NM:i:0  
SOLEXA1\_0917\_FC628DCAAXX:2:92:3430:18241\#0/1 0
gi|295675101|ref|NC\_014117.1| 2620 255 15M \* 0 0 CGATTTCGGCGTCGG
fffffffffffffff XA:i:0 MD:Z:15 NM:i:0  
S
