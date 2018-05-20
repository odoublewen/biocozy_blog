+++
title = "bwa and the -n option (Maximum number of alignments)"
slug = "2012-09-25-bwa-and-the-n-option-maximum-number-of-alignments"
published = 2012-09-25T15:08:00.002000-07:00
author = "Owen"
tags = []
+++
When you ask [bwa](http://bio-bwa.sourceforge.net/) to report multiple
hits, it has a very strange behavior.  
  
I am addressing this behavior, highlighted in bold below, and especially
the part in yellow italic bold (this is from the [bwa
manual](http://bio-bwa.sourceforge.net/bwa.shtml)):  
  

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>samse</strong></td>
<td>bwa samse [-n maxOcc] &gt;<br />

<div style="text-align: justify;">
Generate alignments in the SAM format given single-end reads. Repetitive hits will be randomly chosen.
</div>
<div style="text-align: justify;">
<strong>OPTIONS:</strong><br />

<table>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><strong>-n</strong><em> INT</em></td>
<td>Maximum number of alignments to output in the XA tag for reads paired properly.<span style="background-color: white;"> <strong>If a read has more than INT hits,</strong> </span><strong><em>the XA tag will not be written.</em></strong> [3]</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
</tbody>
</table>

  
  

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>sampe</strong></td>
<td>bwa sampe [-a maxInsSize] [-o maxOcc] [-n maxHitPaired] [-N maxHitDis] [-P] &gt;<br />

<div style="text-align: justify;">
Generate alignments in the SAM format given paired-end reads. Repetitive read pairs will be placed randomly.
</div>
<div style="text-align: justify;">
<strong>OPTIONS:</strong><br />

<table>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><strong>-n</strong><em> INT</em></td>
<td>Maximum number of alignments to output in the XA tag for reads paired properly. <strong>If a read has more than INT hits, t<em>he XA tag will not be written.</em></strong> [3]</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
</tbody>
</table>

  
  
Wait, what?  So you're saying, if there are 10 good hits in a given
index, and I ask for 10, I will get 10 (1 primary plus 9 in the XA tag),
but if I ask for 11, I get only the 1 primary?  Even worse, it pretty
much seems like you have no way of knowing when multiple hits are being
omitted due to this pathological behavior.  
  
I would think that a much more reasonable approach would be to report
***up to*** n hits.  
  
I almost couldn't believe this could be true, so I ran the "bwa sampe"
command on the same sai file, differing only the "n" number (columns in
below table).  The number in the table shows the number of accession
numbers after the XA tag of the bwa sam file (rows in table below).  The
number in the table shows the number of reads that had exactly that
number of reported extra hits.  

  

  

<table style="width:100%;">
<colgroup>
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
<col style="width: 4%" />
</colgroup>
<tbody>
<tr class="odd">
<td><div class="p1">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;"><br />
</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n1.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n2.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n3.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n4.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n5.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n6.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n7.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n8.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n9.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n10.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n11.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n12.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n13.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n14.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n15.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n16.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n17.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n18.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n19.sam</span>
</div></td>
<td><div class="p2">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">bwa_n20.sam</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">22</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10511</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">401</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3821</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">3</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">6919</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">6919</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10357</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">4</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">503</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">503</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">503</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1638</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">5</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">270</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">270</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">270</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">270</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12973</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">6</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">617</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">617</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">617</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">617</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">617</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">36680</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">7</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">85</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">85</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">85</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">85</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">85</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">85</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">515</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">8</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">105</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">105</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">105</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">105</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">105</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">105</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">105</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">2281</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">9</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">14</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">14</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">14</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">14</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">14</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">14</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">14</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">14</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">108</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">10</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">26</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">26</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">26</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">26</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">26</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">26</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">26</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">26</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">26</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">164</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">11</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">125</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">12</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1002</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1002</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1002</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1002</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1002</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1002</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1002</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1002</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1002</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">13</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">75</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">75</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">75</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">75</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">75</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">75</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">75</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">75</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">14</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">866</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">866</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">866</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">866</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">866</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">866</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">866</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">15</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">49</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">49</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">49</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">49</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">49</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">49</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">16</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1072</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1072</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1072</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1072</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1072</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">17</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1321</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1321</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1321</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">1321</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">18</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">161</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">161</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">161</span>
</div></td>
</tr>
<tr class="odd">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">19</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">58</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">58</span>
</div></td>
</tr>
<tr class="even">
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">20</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">0</span>
</div></td>
<td><div class="p3">
<span style="font-family: Courier New, Courier, monospace; font-size: xx-small;">163</span>
</div></td>
</tr>
</tbody>
</table>

  
  
Sure enough, looking at 10 &lt; n &lt; 20, you can see it works pretty
much like the manual says it does... which seems like a shame.
 Considering the [recently added support for indices with 64-bit
addressing](http://www.biostars.org/post/show/52742/how-fundamental-is-the-4-gb-size-limit-for-building-burrows-wheeler-indices/),
bwa could be really useful in metagenomic environmental sampling... but
not if it pathologically erases multiple hits!  
  
There is something else weird going on for n &lt; 10 — my guess is that
it ALWAYS reports up to 10 additional **perfect** hits, if present,
regardless of the n number.
