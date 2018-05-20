+++
title = "Hunting for the perfect codon aware aligner"
slug = "2014-05-16-hunting-for-the-perfect-codon-aware-aligner"
published = 2014-05-16T10:20:00-07:00
author = "Owen"
tags = []
+++
Yesterday I went looking for a well-behaved codon-aware aligner.   A
question that has been brought up on both [Stack
Overflow](http://stackoverflow.com/questions/20843867/codon-alignment-via-python)
and [BioStars](https://www.biostars.org/p/2576/).  
  
  
What I discovered is that many software projects that claim to be codon
aligners are actually just (1) translating the nucleotide sequence to an
amino acid seqeunce, (2) aligning the amino acid sequencing, and (3)
mapping the a.a. alignment structure to the nucleotide sequences, in a
codon-by-codon fashion.  Well, that's fine as far as it goes, but (a) I
can do that myself, and (b) this strategy fails in certain cases (e.g.,
a polymeric stretch of amino acids that have different, synonymous
codons.)  
  
Here are the software programs I tried. Sources are available for all of
them, and most also have web app interfaces (not ultimately what I want
but good for a test drive.)  

-   [TranslatorX](http://translatorx.co.uk/)
    \[[cite](http://nar.oxfordjournals.org/content/38/suppl_2/W7)\] -
    Perl script and web app by Abascal F, Zardoya R, Telford MJ
-   [MACSE](http://mbb.univ-montp2.fr/macse)
    \[[cite](http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0022594)\] -
    Java jar archive by <span class="author" rel="dc:creator"><span
    class="person">Vincent Ranwez at Université Montpellier
    2</span></span>
-   [transAlign](http://www.uni-oldenburg.de/ibu/systematik-evolutionsbiologie/programme/) 
    \[[cite](http://www.biomedcentral.com/1471-2105/6/156/)\] - Perl
    script by Olaf R.P. Bininda-Emonds at University of Oldenburg
-   [PRANK](http://www.ebi.ac.uk/goldman-srv/prank/prank/)
    \[[code](http://code.google.com/p/prank-msa/wiki/PRANK)|[cite](http://www.pnas.org/content/102/30/10557.full)\] -
    C++ program by [Ari Löytynoja](http://blogs.helsinki.fi/sa-at-bi)
    developed in the Goldman lab at EMBL-EBI and now at the University
    of Helsinki
-   [Bio.CodonAlign](https://github.com/zruan/biopython/tree/master/Bio/CodonAlign)
    \[[docs](http://zruanweb.com/)\] - fork of BioPython by Zheng Ruan
    written in a Google Summer of Code 2013

  
  

[PRANK](http://code.google.com/p/prank-msa/wiki/PRANK)The upshot:  only
PRANK seems to be a **true** codon-aware aligner. 

  

  

Wish-list:  What I really want is something like PRANK but that is
streamlined for fast pairwise alignment.  Ideally callable as a Python
module!  Or at least be able to communicate with the binary via stdin
and stout pipes.  Wish I knew some C++ but I don't :/

  
  
<span style="font-weight: normal;">Here are details of my test and the
results I got: </span>  

<span style="font-weight: normal;">Test Sequences</span>
--------------------------------------------------------

  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;">&gt;one  
AGTAAGAAAGCAGCACAGCAA<span
style="background-color: #cccccc;">GCAGCAGCT</span>AACACAGGAAACAGCGGTCAGGTTAGC  
&gt;two  
AGTAAGAAAAAGGAACAGCAG<span
style="background-color: #cccccc;">GCAGCT</span>AACACAGGAAACAGCGGTCAGGTTAGC  
&gt;three  
AGTAAGAAAAAGGAACAGCAG<span
style="background-color: #cccccc;">GCAGCA</span>AACACAGGAAACAGCGGTCAGGTTAGC</span>  
  
  

**<span style="font-weight: normal;">Results from translatorX[](https://www.blogger.com/null)</span>**
------------------------------------------------------------------------------------------------------

  
  

<table>
<tbody>
<tr class="odd">
<td>one</td>
<td>AGT</td>
<td>AAG</td>
<td>AAA</td>
<td>GCA</td>
<td>GCA</td>
<td>CAG</td>
<td>CAA</td>
<td>GCA</td>
<td>GCA</td>
<td>GCT</td>
<td>AAC</td>
<td>ACA</td>
<td>GGA</td>
<td>AAC</td>
<td>AGC</td>
<td>GGT</td>
<td>CAG</td>
<td>GTT</td>
<td>AGC</td>
</tr>
<tr class="even">
<td>two</td>
<td>AGT</td>
<td>AAG</td>
<td>AAA</td>
<td>AAG</td>
<td>GAA</td>
<td>CAG</td>
<td>CAG</td>
<td>---</td>
<td>GCA</td>
<td>GCT</td>
<td>AAC</td>
<td>ACA</td>
<td>GGA</td>
<td>AAC</td>
<td>AGC</td>
<td>GGT</td>
<td>CAG</td>
<td>GTT</td>
<td>AGC</td>
</tr>
<tr class="odd">
<td>three</td>
<td>AGT</td>
<td>AAG</td>
<td>AAA</td>
<td>AAG</td>
<td>GAA</td>
<td>CAG</td>
<td>CAG</td>
<td>---</td>
<td>GCA</td>
<td><strong><span style="color: red;">GCA</span></strong></td>
<td>AAC</td>
<td>ACA</td>
<td>GGA</td>
<td>AAC</td>
<td>AGC</td>
<td>GGT</td>
<td>CAG</td>
<td>GTT</td>
<td>AGC</td>
</tr>
</tbody>
</table>

  
<span style="font-size: small;"><span
style="font-family: &quot;Courier New&quot;,Courier,monospace;">&gt;one  
SKKAAQQAAANTGNSGQVS  
&gt;two  
SKKKEQQ-AANTGNSGQVS  
&gt;three  
SKKKEQQ-AANTGNSGQVS</span></span>  
  
  

**<span style="font-weight: normal;">Results from MACSE</span>**
----------------------------------------------------------------

<span style="font-size: small;">  
</span>  

    >one
    AGTAAGAAAGCAGCACAGCAAGCAGCAGCTAACACAGGAAACAGCGGTCAGGTTAGC
    >two
    AGTAAGAAAAAGGAACAGCAGGCAGCT---AACACAGGAAACAGCGGTCAGGTTAGC
    >three
    AGTAAGAAAAAGGAACAGCAGGCAGCA---AACACAGGAAACAGCGGTCAGGTTAGC 

     

    >one
    SKKAAQQAAANTGNSGQVS
    >two
    SKKKEQQAA-NTGNSGQVS
    >three
    SKKKEQQAA-NTGNSGQVS 

     

  
  

<span style="font-weight: normal;">Results from transAlign[](https://www.blogger.com/null)</span>
-------------------------------------------------------------------------------------------------

  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;">&gt;one  
AGTAAGAAAGCAGCACAGCAAGCAGCAGCTAACACAGGAAACAGCGGTCAGGTTAGC  
&gt;three  
AGTAAGAAAAAGGAACAGCAG---GCA**<span style="color: red;"><span
style="background-color: white;">GCA</span></span>**AACACAGGAAACAGCGGTCAGGTTAGC  
&gt;two  
AGTAAGAAAAAGGAACAGCAG---GCAGCTAACACAGGAAACAGCGGTCAGGTTAGC</span>  
  
  
CLUSTAL 2.1 multiple sequence alignment  
  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;">tAlign\_2       
SKKKEQQ-AANTGNSGQVS  
tAlign\_3        SKKKEQQ-AANTGNSGQVS  
tAlign\_1        SKKAAQQAAANTGNSGQVS  
                \*\*\*  \*\* \*\*\*\*\*\*\*\*\*\*\*</span>  
  
  
  

**<span style="font-weight: normal;">Results from PRANK</span>**
----------------------------------------------------------------

  
(with "align translated codons" option checked)  
  
Curiously, with all three test sequences, it doesn't put the GCT where I
want it...  
  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;">&gt;one  
AGTAAGAAAGCAGCACAGCAAGCAGCAGCTAACACAGGAAACAGCGGTCAGGTTAGC  
&gt;two  
AGTAAGAAAAAGGAACAGCAGGCA**<span
style="color: red;">GCT</span>**---AACACAGGAAACAGCGGTCAGGTTAGC  
&gt;three  
AGTAAGAAAAAGGAACAGCAGGCAGCA---AACACAGGAAACAGCGGTCAGGTTAGC</span>  
  
  
But with seqs 1 and 3, it works correctly...  
  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;">&gt;one  
AGTAAGAAAGCAGCACAGCAAGCAGCAGCTAACACAGGAAACAGCGGTCAGGTTAGC  
&gt;three  
AGTAAGAAAAAGGAACAGCAGGCAGCA---AACACAGGAAACAGCGGTCAGGTTAGC</span>  
   
As it does with just seqs 1 and 2...  
  
<span
style="font-family: &quot;Courier New&quot;,Courier,monospace;">&gt;one  
AGTAAGAAAGCAGCACAGCAAGCAGCAGCTAACACAGGAAACAGCGGTCAGGTTAGC  
&gt;two  
TGGAAGAAAAAGGAACAGCAGGCA---GCTAACACAGGAAACAGCGGTCAGGTTAGC</span>  
  
  
I think the behavior with all 3 seqs is not a glitch but is rather a
result of the probabilistic model that PRANK uses for multiple sequence
alignments (ie, the alignments inform each other.)
