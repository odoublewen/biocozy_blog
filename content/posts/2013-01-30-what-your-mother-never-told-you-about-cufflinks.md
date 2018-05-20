+++
title = "What your mother never told you about cufflinks"
slug = "2013-01-30-what-your-mother-never-told-you-about-cufflinks"
published = 2013-01-30T17:48:00.001000-08:00
author = "Owen"
tags = []
+++
In this post, I am trying to nail down the "best" way to run cufflinks,
part of the so-called "tuxedo suite" of RNA-Seq tools (tophat,
cufflinks, etc.)  
  
I have a dataset composed of 3 technical replicates -- exactly the same
library, run in 3 separate hi-seq lanes (multiplexed along with other
samples, but I am ignoring those for now.) They were run on an Illumina
HiSeq 2000, with 101 bp paired-end reads.  
  
Number of reads, before and after quality trimming and preprocessing:  
  
<span style="font-family: Courier New, Courier, monospace;">Replicate  
Before      After</span>  
<span style="font-family: Courier New, Courier, monospace;">1        
  19,939,455  </span><span
style="font-family: 'Courier New', Courier, monospace;">19,074,425</span>  
<span style="font-family: Courier New, Courier, monospace;">2        
  19,929,909</span><span
style="font-family: 'Courier New', Courier, monospace;">  </span><span
style="font-family: 'Courier New', Courier, monospace;">19,120,424</span>  
<span style="font-family: Courier New, Courier, monospace;">3        
  19,950,587  </span><span
style="font-family: 'Courier New', Courier, monospace;">19,101,188</span>  
<span style="font-family: inherit;">You can see, the lanes were very
uniform in the number of reads.</span>  
<span style="font-family: inherit;">  
</span><span style="font-family: inherit;">For all of the following
commands, I am using the iGenomes files (for the bowtie2 index, the GTF
file, and the genome.fa file), available here: </span>  
<http://ccb.jhu.edu/software/tophat/igenomes.shtml>  
  
<span style="font-family: inherit;">I ran tophat like this:</span>  
<span style="font-family: Courier New, Courier, monospace;">tophat -G
genes.gtf --transcriptome-index=transcriptome -p 8 -o out genome
rep1\_1.fq.gz rep1\_2.fq.gz</span>  
<span style="font-family: inherit;">  
</span><span style="font-family: inherit;">Cufflinks was run like
this:</span>  
<span style="font-family: Courier New, Courier, monospace;">cufflinks -p
24 <span
style="background-color: yellow;">--no-effective-length-correction</span>
<span style="background-color: #ead1dc;">-b genome.fa</span> -G
genes.gtf -o out out/accepted\_hits.bam</span>  
<span style="font-family: inherit;">  
</span><span style="font-family: inherit;">The two variables are
highlighted.  </span>  
<span style="font-family: inherit;">  
</span><span style="font-family: inherit;">The cufflinks online manual
says (note, "Cuffdiff" is a typo and should read "Cufflinks")</span>  
<span style="font-family: inherit;">  
</span>  

<table>
<tbody>
<tr class="odd">
<td><code style="font-family: &#39;Courier New&#39;, Courier, monospace; margin: 0px; padding: 0px;">--no-effective-length-correction</code></td>
<td>Cuffdiff will not employ its &quot;effective&quot; length normalization to transcript FPKM.</td>
</tr>
</tbody>
</table>

  
and:  
  

<table>
<tbody>
<tr class="odd">
<td><code style="font-family: &#39;Courier New&#39;, Courier, monospace; margin: 0px; padding: 0px;">-b/--frag-bias-correct </code></td>
<td>Providing Cufflinks with the multifasta file your reads were mapped to via this option instructs it to run our bias detection and correction algorithm which can significantly improve accuracy of transcript abundance estimates. See <a href="http://cole-trapnell-lab.github.io/cufflinks/how_it_works/index.html">How Cufflinks Works</a> for more details.</td>
</tr>
</tbody>
</table>

  
For each run, I sorted the resulting genes.fpkm\_tracking files, pulled
out the FPKM column, and calculated the mean of the pairwise Pearson
correlation for the 3 replicates. Here are the results:  
  
  

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><div class="MsoNormal">
effective length corr
</div></td>
<td><div class="MsoNormal">
fragment bias corr
</div></td>
<td><div class="MsoNormal">
Time
</div></td>
<td><div class="MsoNormal">
Correlation
</div></td>
</tr>
<tr class="even">
<td><div class="MsoNormal">
Yes
</div></td>
<td><div class="MsoNormal">
Yes
</div></td>
<td><div class="MsoNormal">
43 min
</div></td>
<td><div class="MsoNormal">
0.9790755
</div></td>
</tr>
<tr class="odd">
<td><div class="MsoNormal">
Yes
</div></td>
<td><div class="MsoNormal">
No
</div></td>
<td><div class="MsoNormal">
16 min
</div></td>
<td><div class="MsoNormal">
0.9749819
</div></td>
</tr>
<tr class="even">
<td><div class="MsoNormal">
No
</div></td>
<td><div class="MsoNormal">
Yes
</div></td>
<td><div class="MsoNormal">
43 min
</div></td>
<td><div class="MsoNormal">
0.9999465
</div></td>
</tr>
<tr class="odd">
<td><div class="MsoNormal">
No
</div></td>
<td><div class="MsoNormal">
No
</div></td>
<td><div class="MsoNormal">
16 min
</div></td>
<td><div class="MsoNormal">
0.9999626
</div></td>
</tr>
</tbody>
</table>

  
  
Note: the effective length correction is on by default, whereas the frag
bias correction is off by default.  
  
**The best way to run cufflinks is with --no-effective-length-correction
!!!**  
**  
frag-bias-correction makes the analysis much slower, without any
discernable benefit in this trial run.**
