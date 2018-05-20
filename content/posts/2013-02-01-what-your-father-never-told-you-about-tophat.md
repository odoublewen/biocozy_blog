+++
title = "What your father never told you about tophat"
slug = "2013-02-01-what-your-father-never-told-you-about-tophat"
published = 2013-02-01T14:16:00.001000-08:00
author = "Owen"
tags = []
+++
Following up on yesterday's [posting about the "right" way to run
cufflinks](http://biocozy.blogspot.com/2013/01/what-your-mother-never-told-you-about.html),
I am here recording my experiences running tophat with and without the
--no-novel-juncs setting.  
  
Same dataset as described in the previous posting.  Still using the
Illumina iGenomes Ensembl annotation files. The command I used was like
this (note: the transcriptome index was pre-built during a previous
run.)  
  
tophat \[--no-novel-juncs\] -G genes.gtf
--transcriptome-index=transcriptome -p 8 -o tophat\_out file\_1.fq.gz
file\_2.fq.gz  
  
Mean run time for the three replicates (which have very nearly the same
number of reads, about 19 million each):  
Default (with novel junction finding): 160 minutes  
With --no-novel-juncs option:  150 minutes  
  
No big time savings from turning off novel junction finding.  No
difference in the mean correlation of genes.fpkm\_tracking from the
resultant cufflinks run.  
  
Also, I tried --no-novel-juncs with 8, 16, and 24 processors, on a
server with 32 cores (not hyperthreaded).  
  
8 procs = 150 minutes  
16 procs = 134 minutes  
24 procs = 121 minutes  
  
Tophat basically parallelizes the bowtie2 alignment stage, but there is
a lot of time spent reading and writing files, which is
single-threaded.  
  
I have, in the past, had problems with tophat [dying when running with
too many
processors](http://seqanswers.com/forums/showthread.php?t=24995) (24,
for instance) but the failure is not predictable:  
  
  
<span
style="font-family: Courier New, Courier, monospace; font-size: xx-small;">\[2013-02-05
08:08:09\] Mapping right\_kept\_reads.m2g\_um\_seg2 to genome
segment\_juncs with Bowtie2 (2/4)</span>  
<span
style="font-family: Courier New, Courier, monospace; font-size: xx-small;">\[2013-02-05
08:08:34\] Mapping right\_kept\_reads.m2g\_um\_seg3 to genome
segment\_juncs with Bowtie2 (3/4)</span>  
<span
style="font-family: Courier New, Courier, monospace; font-size: xx-small;">\[2013-02-05
08:09:01\] Mapping right\_kept\_reads.m2g\_um\_seg4 to genome
segment\_juncs with Bowtie2 (4/4)</span>  
<span
style="font-family: Courier New, Courier, monospace; font-size: xx-small;">\[2013-02-05
08:09:25\] Joining segment hits</span>  
<span
style="font-family: Courier New, Courier, monospace; font-size: xx-small;">\[2013-02-05
08:11:22\] Reporting output tracks</span>  
<span
style="font-family: Courier New, Courier, monospace; font-size: xx-small;"> 
      \[FAILED\]</span>  
<span
style="font-family: Courier New, Courier, monospace; font-size: xx-small;">Error
running /usr/local/tophat-2.0.7.Linux\_x86\_64/tophat\_reports
--min-anchor 8 --splice-mismatches 0 --min-report-intron 50
--max-report-intron 500000 --min-isoform-fraction 0.15 --output-dir
Sample\_04\_L005/ --max-multihits 20 --max-seg-multihits 40
--segment-length 25 --segment-mismatches 2 --min-closure-exon 100
--min-closure-intron 50 --max-closure-intron 5000 --min-coverage-intron
50 --max-coverage-intron 20000 --min-segment-intron 50
--max-segment-intron 500000 --read-mismatches 2 --read-gap-length 2
--read-edit-dist 2 --read-realign-edit-dist 3 --max-insertion-length 3
--max-deletion-length 3 -z gzip -p24 --inner-dist-mean 50
--inner-dist-std-dev 20 --gtf-annotations
/data/genomes/iGenomes/Ensembl/transcriptome.gff --gtf-juncs
Sample\_04\_L005/tmp/transcriptome.juncs --no-closure-search
--no-coverage-search --no-microexon-search --sam-header
Sample\_04\_L005/tmp/genome\_genome.bwt.samheader.sam
--report-discordant-pair-alignments --report-mixed-alignments
--samtools=/usr/local/samtools/samtools --bowtie2-max-penalty 6
--bowtie2-min-penalty 2 --bowtie2-penalty-for-N 1
--bowtie2-read-gap-open 5 --bowtie2-read-gap-cont 3
--bowtie2-ref-gap-open 5 --bowtie2-ref-gap-cont 3
/data/genomes/iGenomes/Ensembl/genome.fa Sample\_04\_L005/junctions.bed
Sample\_04\_L005/insertions.bed Sample\_04\_L005/deletions.bed
Sample\_04\_L005/fusions.out Sample\_04\_L005/tmp/accepted\_hits
Sample\_04\_L005/tmp/left\_kept\_reads.m2g.bam,Sample\_04\_L005/tmp/left\_kept\_reads.m2g\_um.mapped.bam,Sample\_04\_L005/tmp/left\_kept\_reads.m2g\_um.candidates
Sample\_04\_L005/tmp/left\_kept\_reads.bam
Sample\_04\_L005/tmp/right\_kept\_reads.m2g.bam,Sample\_04\_L005/tmp/right\_kept\_reads.m2g\_um.mapped.bam,Sample\_04\_L005/tmp/right\_kept\_reads.m2g\_um.candidates
Sample\_04\_L005/tmp/right\_kept\_reads.bam</span>  
<span
style="font-family: Courier New, Courier, monospace; font-size: xx-small;">**Error:
bam\_merge failed to open BAM file
Sample\_04\_L005/tmp/right\_kept\_reads.m2g\_um.candidates15.bam**</span>
