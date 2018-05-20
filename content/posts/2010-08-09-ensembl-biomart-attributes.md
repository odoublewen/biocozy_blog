+++
title = "Ensembl Biomart Attributes"
slug = "2010-08-09-ensembl-biomart-attributes"
published = 2010-08-09T12:52:00-07:00
author = "Owen"
tags = []
+++
Here is the list, current as of posting, for the ensembl biomart
attributes available from within R/Bioconductor...  
  
name description  
1 ensembl\_gene\_id Ensembl Gene ID  
2 ensembl\_transcript\_id Ensembl Transcript ID  
3 ensembl\_peptide\_id Ensembl Protein ID  
4 canonical\_transcript\_stable\_id Canonical transcript stable ID(s)  
5 description Description  
6 chromosome\_name Chromosome Name  
7 start\_position Gene Start (bp)  
8 end\_position Gene End (bp)  
9 strand Strand  
10 band Band  
11 transcript\_start Transcript Start (bp)  
12 transcript\_end Transcript End (bp)  
13 external\_gene\_id Associated Gene Name  
14 external\_transcript\_id Associated Transcript Name  
15 external\_gene\_db Associated Gene DB  
16 transcript\_db\_name Associated Transcript DB  
17 transcript\_count Transcript count  
18 percentage\_gc\_content % GC content  
19 gene\_biotype Gene Biotype  
20 transcript\_biotype Transcript Biotype  
21 source Source  
22 status Status (gene)  
23 transcript\_status Status (transcript)  
24 go\_biological\_process\_id GO Term Accession (bp)  
25 name\_1006 GO Term Name (bp)  
26 definition\_1006 GO Term Definition (bp)  
27 go\_biological\_process\_linkage\_type GO Term Evidence Code (bp)  
28 go\_cellular\_component\_id GO Term Accession (cc)  
29 go\_cellular\_component\_\_dm\_name\_1006 GO Term Name (cc)  
30 go\_cellular\_component\_\_dm\_definition\_1006 GO Term Definition
(cc)  
31 go\_cellular\_component\_linkage\_type GO Term Evidence Code (cc)  
32 go\_molecular\_function\_id GO Term Accession  
33 go\_molecular\_function\_\_dm\_name\_1006 GO Term Name (mf)  
34 go\_molecular\_function\_\_dm\_definition\_1006 GO Term Definition
(mf)  
35 go\_molecular\_function\_linkage\_type GO Term Evidence Code (mf)  
36 goslim\_goa\_accession GOSlim GOA Accession(s)  
37 goslim\_goa\_description GOSlim GOA Description  
38 ucsc UCSC ID  
39 pdb PDB ID  
40 clone\_based\_ensembl\_gene\_name Clone based Ensembl gene name  
41 clone\_based\_ensembl\_transcript\_name Clone based Ensembl
transcript name  
42 clone\_based\_vega\_gene\_name Clone based VEGA gene name  
43 clone\_based\_vega\_transcript\_name Clone based VEGA transcript
name  
44 ccds CCDS ID  
45 embl EMBL (Genbank) ID  
46 ox\_ens\_lrg\_transcript\_\_dm\_dbprimary\_acc\_1074 Ensembl LRG
transcript  
47 entrezgene EntrezGene ID  
48 ottt VEGA transcript ID(s) (OTTT)  
49 ottg VEGA gene ID(s) (OTTG)  
50 shares\_cds\_with\_enst Ensembl transcript (where OTTT shares CDS
with ENST)  
51 shares\_cds\_with\_ottt HAVANA transcript (where ENST shares CDS with
OTTT)  
52 shares\_cds\_and\_utr\_with\_ottt HAVANA transcript (where ENST
identical to OTTT)  
53 hgnc\_id HGNC ID  
54 hgnc\_symbol HGNC symbol  
55 hgnc\_automatic\_gene\_name HGNC automatic gene name  
56 hgnc\_curated\_gene\_name HGNC curated gene name  
57 hgnc\_automatic\_transcript\_name HGNC automatic transcript name  
58 hgnc\_curated\_transcript\_name HGNC curated transcript name  
59 hgnc\_mb001 HGNC mb001 ID  
60 ipi IPI ID  
61 merops MEROPS ID  
62 mim\_morbid\_accession MIM Morbid Accession  
63 mim\_morbid\_description MIM Morbid Description  
64 mim\_gene\_accession MIM Gene Accession  
65 mim\_gene\_description MIM Gene Description  
66 mirbase\_accession miRBase Accession(s)  
67 mirbase\_id miRBase ID(s)  
68 protein\_id Protein (Genbank) ID  
69 refseq\_dna RefSeq DNA ID  
70 refseq\_dna\_predicted RefSeq Predicted DNA ID  
71 refseq\_peptide RefSeq Protein ID  
72 refseq\_peptide\_predicted RefSeq Predicted Protein ID  
73 refseq\_genomic RefSeq Genomic ID(s)  
74 rfam Rfam ID  
75 unigene Unigene ID  
76 uniprot\_sptrembl UniProt/TrEMBL Accession  
77 uniprot\_swissprot\_accession UniProt/SwissProt Accession  
78 wikigene\_name WikiGene name  
79 wikigene\_description WikiGene description  
80 hpa Human Protein Atlas Antibody ID  
81 dbass3\_id Database of Aberrant 3' Splice Sites (DBASS3) IDs  
82 dbass3\_name DBASS3 Gene Name  
83 dbass5\_id Database of Aberrant 5' Splice Sites (DBASS5) IDs  
84 dbass5\_name DBASS5 Gene Name  
85 affy\_hc\_g110 Affy HC G110  
86 affy\_hg\_focus Affy HG FOCUS  
87 affy\_hg\_u133\_plus\_2 Affy HG U133-PLUS-2  
88 affy\_hg\_u133a\_2 Affy HG U133A\_2  
89 affy\_hg\_u133a Affy HG U133A  
90 affy\_hg\_u133b Affy HG U133B  
91 affy\_hg\_u95av2 Affy HG U95AV2  
92 affy\_hg\_u95b Affy HG U95B  
93 affy\_hg\_u95c Affy HG U95C  
94 affy\_hg\_u95d Affy HG U95D  
95 affy\_hg\_u95e Affy HG U95E  
96 affy\_hg\_u95a Affy HG U95A  
97 affy\_hugenefl Affy HuGene FL  
98 affy\_huex\_1\_0\_st\_v2 Affy HuEx 1\_0 st v2  
99 affy\_hugene\_1\_0\_st\_v1 Affy HuGene 1\_0 st v1  
100 affy\_u133\_x3p Affy U133 X3P  
101 agilent\_cgh\_44b Agilent CGH 44b  
102 agilent\_wholegenome Agilent WholeGenome  
103 codelink Codelink  
104 illumina\_humanwg\_6\_v1 Illumina HumanWG 6 v1  
105 illumina\_humanwg\_6\_v2 Illumina HumanWG 6 v2  
106 illumina\_humanwg\_6\_v3 Illumina HumanWG 6 v3  
107 illumina\_humanht\_12 Illumina Human HT 12  
108 phalanx\_onearray Phalanx OneArray  
109 anatomical\_system Anatomical System (egenetics)  
110 development\_stage Development Stage (egenetics)  
111 cell\_type Cell Type (egenetics)  
112 pathology Pathology (egenetics)  
113 anatomical\_system\_gnf Anatomical System (gnf)  
114 development\_stage\_gnf Development Stage (gnf)  
115 cell\_type\_gnf Cell Type (gnf)  
116 pathology\_gnf Pathology (gnf)  
117 family\_description Ensembl Family Description  
118 family Ensembl Protein Family ID(s)  
119 pirsf PIRSF SuperFamily ID  
120 superfamily Superfamily ID  
121 smart SMART ID  
122 profile PROFILE ID  
123 prosite PROSITE ID  
124 prints PRINTS ID  
125 pfam PFAM ID  
126 tigrfam TIGRFam ID  
127 interpro Interpro ID  
128 interpro\_short\_description Interpro Short Description  
129 interpro\_description Interpro Description  
130 transmembrane\_domain Transmembrane domain  
131 signal\_domain Signal domain  
132 ncoils Ncoils  
133 ensembl\_gene\_id Ensembl Gene ID  
134 ensembl\_transcript\_id Ensembl Transcript ID  
135 ensembl\_peptide\_id Ensembl Protein ID  
136 chromosome\_name Chromosome Name  
137 start\_position Gene Start (bp)  
138 end\_position Gene End (bp)  
139 transcript\_start Transcript Start (bp)  
140 transcript\_end Transcript End (bp)  
141 strand Strand  
142 external\_gene\_id Associated Gene Name  
143 external\_gene\_db Associated Gene DB  
144 5\_utr\_start 5' UTR Start  
145 5\_utr\_end 5' UTR End  
146 3\_utr\_start 3' UTR Start  
147 3\_utr\_end 3' UTR End  
148 cds\_length CDS Length  
149 transcript\_count Transcript count  
150 description Description  
151 gene\_biotype Gene Biotype  
152 ensembl\_exon\_id Ensembl Exon ID  
153 exon\_chrom\_start Exon Chr Start (bp)  
154 exon\_chrom\_end Exon Chr End (bp)  
155 is\_constitutive Constitutive Exon  
156 rank Exon Rank in Transcript  
157 phase phase  
158 cdna\_coding\_start cDNA coding start  
159 cdna\_coding\_end cDNA coding end  
160 genomic\_coding\_start Genomic coding start  
161 genomic\_coding\_end Genomic coding end  
162 cds\_start CDS Start  
163 cds\_end CDS End  
164 ensembl\_gene\_id Ensembl Gene ID  
165 ensembl\_transcript\_id Ensembl Transcript ID  
166 ensembl\_peptide\_id Ensembl Protein ID  
167 ensembl\_exon\_id Ensembl Exon ID  
168 name\_1078 Gene Name With Corresponding Event  
169 splicing\_event\_\_dm\_name\_1059 Chromosome Name  
170 seq\_region\_start\_1078 Seq Region Start (bp)  
171 seq\_region\_end\_1078 Seq Region End (bp)  
172 seq\_region\_strand\_1078 Strand  
173 ensembl\_gene\_id Ensembl Gene ID  
174 ensembl\_transcript\_id Ensembl Transcript ID  
175 ensembl\_peptide\_id Ensembl Protein ID  
176 chromosome\_name Chromosome Name  
177 start\_position Gene Start (bp)  
178 end\_position Gene End (bp)  
179 strand Strand  
180 band Band  
181 external\_gene\_id Associated Gene Name  
182 external\_gene\_db Associated Gene DB  
183 transcript\_count Transcript count  
184 percentage\_gc\_content % GC content  
185 description Description  
186 alpaca\_ensembl\_gene Alpaca Ensembl Gene ID  
187 alpaca\_homolog\_ensembl\_peptide Alpaca Ensembl Protein ID  
188 alpaca\_chromosome Alpaca Chromosome  
189 alpaca\_chrom\_start Alpaca Chromosome Start (bp)  
190 alpaca\_chrom\_end Alpaca Chromosome End (bp)  
191 alpaca\_orthology\_type Homology Type  
192 alpaca\_homolog\_subtype Ancestor  
193 alpaca\_homolog\_dn dS  
194 alpaca\_homolog\_ds dN  
195 alpaca\_homolog\_perc\_id % Identity  
196 alpaca\_homolog\_perc\_id\_r1 Alpaca % Identity  
197 anole\_lizard\_ensembl\_gene Anole Lizard Ensembl Gene ID  
198 anole\_lizard\_ensembl\_peptide Anole Lizard Ensembl Protein ID  
199 anole\_lizard\_chromosome Anole Lizard Chromosome  
200 anole\_lizard\_chrom\_start Anole Lizard Chromosome Start (bp)  
201 anole\_lizard\_chrom\_end Anole Lizard Chromosome End (bp)  
202 anole\_lizard\_orthology\_type Homology Type  
203 anole\_lizard\_homolog\_subtype Ancestor  
204 anole\_lizard\_homolog\_dn dS  
205 anole\_lizard\_homolog\_ds dN  
206 anole\_lizard\_perc\_id % Identity  
207 anole\_lizard\_perc\_id\_r1 Anole Lizard % Identity  
208 armadillo\_ensembl\_gene Armadillo Ensembl Gene ID  
209 armadillo\_homolog\_ensembl\_peptide Armadillo Ensembl Protein ID  
210 armadillo\_chromosome Armadillo Chromosome  
211 armadillo\_chrom\_start Armadillo Chromosome Start (bp)  
212 armadillo\_chrom\_end Armadillo Chromosome End (bp)  
213 armadillo\_orthology\_type Homology Type  
214 armadillo\_homolog\_subtype Ancestor  
215 armadillo\_homolog\_dn dS  
216 armadillo\_homolog\_ds dN  
217 armadillo\_homolog\_perc\_id % Identity  
218 armadillo\_homolog\_perc\_id\_r1 Armadillo % Identity  
219 bushbaby\_ensembl\_gene Bushbaby Ensembl Gene ID  
220 bushbaby\_homolog\_ensembl\_peptide Bushbaby Ensembl Protein ID  
221 bushbaby\_chromosome Bushbaby Chromosome  
222 bushbaby\_chrom\_start Bushbaby Chromosome Start (bp)  
223 bushbaby\_chrom\_end Bushbaby Chromosome End (bp)  
224 bushbaby\_orthology\_type Homology Type  
225 bushbaby\_homolog\_subtype Ancestor  
226 bushbaby\_homolog\_dn dS  
227 bushbaby\_homolog\_ds dN  
228 bushbaby\_homolog\_perc\_id % Identity  
229 bushbaby\_homolog\_perc\_id\_r1 Bushbaby % Identity  
230 cat\_ensembl\_gene Cat Ensembl Gene ID  
231 cat\_homolog\_ensembl\_peptide Cat Ensembl Protein ID  
232 cat\_chromosome Cat Chromosome  
233 cat\_chrom\_start Cat Chromosome Start (bp)  
234 cat\_chrom\_end Cat Chromosome End (bp)  
235 cat\_orthology\_type Homology Type  
236 cat\_homolog\_subtype Ancestor  
237 cat\_homolog\_dn dS  
238 cat\_homolog\_ds dN  
239 cat\_homolog\_perc\_id % Identity  
240 cat\_homolog\_perc\_id\_r1 Cat % Identity  
241 chicken\_ensembl\_gene Chicken Ensembl Gene ID  
242 chicken\_homolog\_ensembl\_peptide Chicken Ensembl Protein ID  
243 chicken\_chromosome Chicken Chromosome  
244 chicken\_chrom\_start Chicken Chromosome Start (bp)  
245 chicken\_chrom\_end Chicken Chromosome End (bp)  
246 chicken\_orthology\_type Homology Type  
247 chicken\_homolog\_subtype Ancestor  
248 chicken\_homolog\_dn dS  
249 chicken\_homolog\_ds dN  
250 chicken\_homolog\_perc\_id % Identity  
251 chicken\_homolog\_perc\_id\_r1 Chicken % Identity  
252 chimp\_ensembl\_gene Chimp Ensembl Gene ID  
253 chimp\_homolog\_ensembl\_peptide Chimp Ensembl Protein ID  
254 chimp\_chromosome Chimp Chromosome  
255 chimp\_chrom\_start Chimp Chromosome Start (bp)  
256 chimp\_chrom\_end Chimp Chromosome End (bp)  
257 chimp\_orthology\_type Homology Type  
258 chimp\_homolog\_subtype Ancestor  
259 chimp\_homolog\_dn dS  
260 chimp\_homolog\_ds dN  
261 chimp\_homolog\_perc\_id % Identity  
262 chimp\_homolog\_perc\_id\_r1 Chimp % Identity  
263 ciona\_intestinalis\_ensembl\_gene Ciona intestinalis Ensembl Gene
ID  
264 ciona\_intestinalis\_homolog\_ensembl\_peptide Ciona intestinalis
Ensembl Protein ID  
265 ciona\_intestinalis\_chromosome Ciona intestinalis Chromosome  
266 ciona\_intestinalis\_chrom\_start Ciona intestinalis Chromosome
Start (bp)  
267 ciona\_intestinalis\_chrom\_end Ciona intestinalis Chromosome End
(bp)  
268 ciona\_intestinalis\_orthology\_type Homology Type  
269 ciona\_intestinalis\_homolog\_subtype Ancestor  
270 ciona\_intestinalis\_homolog\_dn dS  
271 ciona\_intestinalis\_homolog\_ds dN  
272 ciona\_intestinalis\_homolog\_perc\_id % Identity  
273 ciona\_intestinalis\_homolog\_perc\_id\_r1 Ciona intestinalis %
Identity  
274 ciona\_savignyi\_ensembl\_gene Ciona savignyi Ensembl Gene ID  
275 ciona\_savignyi\_homolog\_ensembl\_peptide Ciona savignyi Ensembl
Protein ID  
276 ciona\_savignyi\_chromosome Ciona savignyi Chromosome  
277 ciona\_savignyi\_chrom\_start Ciona savignyi Chromosome Start (bp)  
278 ciona\_savignyi\_chrom\_end Ciona savignyi Chromosome End (bp)  
279 ciona\_savignyi\_orthology\_type Homology Type  
280 ciona\_savignyi\_homolog\_subtype Ancestor  
281 ciona\_savignyi\_homolog\_dn dS  
282 ciona\_savignyi\_homolog\_ds dN  
283 ciona\_savignyi\_homolog\_perc\_id % Identity  
284 ciona\_savignyi\_homolog\_perc\_id\_r1 Ciona savignyi % Identity  
285 common\_shrew\_ensembl\_gene Common Shrew Ensembl Gene ID  
286 common\_shrew\_homolog\_ensembl\_peptide Common Shrew Ensembl
Protein ID  
287 common\_shrew\_chromosome Common Shrew Chromosome  
288 common\_shrew\_chrom\_start Common Shrew Chromosome Start (bp)  
289 common\_shrew\_chrom\_end Common Shrew Chromosome End (bp)  
290 common\_shrew\_orthology\_type Homology Type  
291 common\_shrew\_homolog\_subtype Ancestor  
292 common\_shrew\_homolog\_dn dS  
293 common\_shrew\_homolog\_ds dN  
294 common\_shrew\_homolog\_perc\_id % Identity  
295 common\_shrew\_homolog\_perc\_id\_r1 Common Shrew % Identity  
296 cow\_homolog\_subtype Ancestor  
297 cow\_ensembl\_gene Cow Ensembl Gene ID  
298 cow\_homolog\_ensembl\_peptide Cow Ensembl Protein ID  
299 cow\_chromosome Cow Chromosome  
300 cow\_chrom\_start Cow Chromosome Start (bp)  
301 cow\_chrom\_end Cow Chromosome End (bp)  
302 cow\_orthology\_type Homology Type  
303 cow\_homolog\_dn dS  
304 cow\_homolog\_ds dN  
305 cow\_homolog\_perc\_id % Identity  
306 cow\_homolog\_perc\_id\_r1 Cow % Identity  
307 dog\_ensembl\_gene Dog Ensembl Gene ID  
308 dog\_homolog\_ensembl\_peptide Dog Ensembl Protein ID  
309 dog\_chromosome Dog Chromosome  
310 dog\_chrom\_start Dog Chromosome Start (bp)  
311 dog\_chrom\_end Dog Chromosome End (bp)  
312 dog\_orthology\_type Homology Type  
313 dog\_homolog\_subtype Ancestor  
314 dog\_homolog\_dn dS  
315 dog\_homolog\_ds dN  
316 dog\_homolog\_perc\_id % Identity  
317 dog\_homolog\_perc\_id\_r1 Dog % Identity  
318 dolphin\_ensembl\_gene Dolphin Ensembl Gene ID  
319 dolphin\_homolog\_ensembl\_peptide Dolphin Ensembl Protein ID  
320 dolphin\_chromosome Dolphin Chromosome  
321 dolphin\_chrom\_start Dolphin Chromosome Start (bp)  
322 dolphin\_chrom\_end Dolphin Chromosome End (bp)  
323 dolphin\_orthology\_type Homology Type  
324 dolphin\_homolog\_subtype Ancestor  
325 dolphin\_homolog\_dn dS  
326 dolphin\_homolog\_ds dN  
327 dolphin\_homolog\_perc\_id % Identity  
328 dolphin\_homolog\_perc\_id\_r1 Dolphin % Identity  
329 drosophila\_ensembl\_gene Drosophila Ensembl Gene ID  
330 drosophila\_homolog\_ensembl\_peptide Drosophila Ensembl Protein
ID  
331 drosophila\_chromosome Drosophila Chromosome  
332 drosophila\_chrom\_start Drosophila Chromosome Start (bp)  
333 drosophila\_chrom\_end Drosophila Chromosome End (bp)  
334 drosophila\_orthology\_type Homology Type  
335 drosophila\_homolog\_subtype Ancestor  
336 drosophila\_homolog\_dn dS  
337 drosophila\_homolog\_ds dN  
338 drosophila\_homolog\_perc\_id % Identity  
339 drosophila\_homolog\_perc\_id\_r1 Drosophila % Identity  
340 elegans\_ensembl\_gene Elegans Ensembl Gene ID  
341 elegans\_homolog\_ensembl\_peptide Elegans Ensembl Protein ID  
342 elegans\_chromosome Elegans Chromosome  
343 elegans\_chrom\_start Elegans Chromosome Start (bp)  
344 elegans\_chrom\_end Elegans Chromosome End (bp)  
345 elegans\_orthology\_type Homology Type  
346 elegans\_homolog\_subtype Ancestor  
347 elegans\_homolog\_dn dS  
348 elegans\_homolog\_ds dN  
349 elegans\_homolog\_perc\_id % Identity  
350 elegans\_homolog\_perc\_id\_r1 Elegans % Identity  
351 elephant\_ensembl\_gene Elephant Ensembl Gene ID  
352 elephant\_homolog\_ensembl\_peptide Elephant Ensembl Protein ID  
353 elephant\_chromosome Elephant Chromosome  
354 elephant\_chrom\_start Elephant Chromosome Start (bp)  
355 elephant\_chrom\_end Elephant Chromosome End (bp)  
356 elephant\_orthology\_type Homology Type  
357 elephant\_homolog\_subtype Ancestor  
358 elephant\_homolog\_dn dS  
359 elephant\_homolog\_ds dN  
360 elephant\_homolog\_perc\_id % Identity  
361 elephant\_homolog\_perc\_id\_r1 Elephant % Identity  
362 xenopus\_ensembl\_gene Frog Ensembl Gene ID  
363 xenopus\_homolog\_ensembl\_peptide Frog Ensembl Protein ID  
364 xenopus\_chromosome Frog Chromosome  
365 xenopus\_chrom\_start Frog Chromosome Start (bp)  
366 xenopus\_chrom\_end Frog Chromosome End (bp)  
367 xenopus\_orthology\_type Homology Type  
368 xenopus\_homolog\_subtype Ancestor  
369 xenopus\_homolog\_dn dS  
370 xenopus\_homolog\_ds dN  
371 xenopus\_homolog\_perc\_id % Identity  
372 xenopus\_homolog\_perc\_id\_r1 Frog % Identity  
373 fugu\_ensembl\_gene Fugu Ensembl Gene ID  
374 fugu\_homolog\_ensembl\_peptide Fugu Ensembl Protein ID  
375 fugu\_chromosome Fugu Chromosome  
376 fugu\_chrom\_start Fugu Chromosome Start (bp)  
377 fugu\_chrom\_end Fugu Chromosome End (bp)  
378 fugu\_orthology\_type Homology Type  
379 fugu\_homolog\_subtype Ancestor  
380 fugu\_homolog\_dn dS  
381 fugu\_homolog\_ds dN  
382 fugu\_homolog\_perc\_id % Identity  
383 fugu\_homolog\_perc\_id\_r1 Fugu % Identity  
384 gorilla\_ensembl\_gene Gorilla Ensembl Gene ID  
385 gorilla\_homolog\_ensembl\_peptide Gorilla Ensembl Protein ID  
386 gorilla\_chromosome Gorilla Chromosome  
387 gorilla\_chrom\_start Gorilla Chromosome Start (bp)  
388 gorilla\_chrom\_end Gorilla Chromosome End (bp)  
389 gorilla\_orthology\_type Homology Type  
390 gorilla\_homolog\_subtype Ancestor  
391 gorilla\_homolog\_dn dS  
392 gorilla\_homolog\_ds dN  
393 gorilla\_homolog\_perc\_id % Identity  
394 gorilla\_homolog\_perc\_id\_r1 Gorilla % Identity  
395 guineapig\_ensembl\_gene Guinea Pig Ensembl Gene ID  
396 guineapig\_homolog\_ensembl\_peptide Guinea Pig Ensembl Protein ID  
397 guineapig\_chromosome Guinea Pig Chromosome  
398 guineapig\_chrom\_start Guinea Pig Chromosome Start (bp)  
399 guineapig\_chrom\_end Guinea Pig Chromosome End (bp)  
400 guineapig\_orthology\_type Homology Type  
401 guineapig\_homolog\_subtype Ancestor  
402 guineapig\_homolog\_dn dS  
403 guineapig\_homolog\_ds dN  
404 guineapig\_homolog\_perc\_id % Identity  
405 guineapig\_homolog\_perc\_id\_r1 Guinea Pig % Identity  
406 hedgehog\_ensembl\_gene Hedgehog Ensembl Gene ID  
407 hedgehog\_homolog\_ensembl\_peptide Hedgehog Ensembl Protein ID  
408 hedgehog\_chromosome Hedgehog Chromosome  
409 hedgehog\_chrom\_start Hedgehog Chromosome Start (bp)  
410 hedgehog\_chrom\_end Hedgehog Chromosome End (bp)  
411 hedgehog\_orthology\_type Homology Type  
412 hedgehog\_homolog\_subtype Ancestor  
413 hedgehog\_homolog\_dn dS  
414 hedgehog\_homolog\_ds dN  
415 hedgehog\_homolog\_perc\_id % Identity  
416 hedgehog\_homolog\_perc\_id\_r1 Hedgehog % Identity  
417 horse\_ensembl\_gene Horse Ensembl Gene ID  
418 horse\_homolog\_ensembl\_peptide Horse Ensembl Protein ID  
419 horse\_chromosome Horse Chromosome  
420 horse\_chrom\_start Horse Chromosome Start (bp)  
421 horse\_chrom\_end Horse Chromosome End (bp)  
422 horse\_orthology\_type Homology Type  
423 horse\_homolog\_subtype Ancestor  
424 horse\_homolog\_dn dS  
425 horse\_homolog\_ds dN  
426 horse\_homolog\_perc\_id % Identity  
427 horse\_homolog\_perc\_id\_r1 Horse % Identity  
428 dordii\_ensembl\_gene Kangaroo Ensembl Gene ID  
429 dordii\_homolog\_ensembl\_peptide Kangaroo Ensembl Protein ID  
430 dordii\_chromosome Kangaroo Chromosome  
431 dordii\_chrom\_start Kangaroo Chromosome Start (bp)  
432 dordii\_chrom\_end Kangaroo Chromosome End (bp)  
433 dordii\_orthology\_type Homology Type  
434 dordii\_homolog\_subtype Ancestor  
435 dordii\_homolog\_dn dS  
436 dordii\_homolog\_ds dN  
437 dordii\_homolog\_perc\_id % Identity  
438 dordii\_homolog\_perc\_id\_r1 Kangaroo % Identity  
439 mmur\_ensembl\_gene M.murinus Ensembl Gene ID  
440 mmur\_homolog\_ensembl\_peptide M.murinus Ensembl Protein ID  
441 mmur\_chromosome M.murinus Chromosome  
442 mmur\_chrom\_start M.murinus Chromosome Start (bp)  
443 mmur\_chrom\_end M.murinus Chromosome End (bp)  
444 mmur\_orthology\_type Homology Type  
445 mmur\_homolog\_subtype Ancestor  
446 mmur\_homolog\_dn dS  
447 mmur\_homolog\_ds dN  
448 mmur\_homolog\_perc\_id % Identity  
449 mmur\_homolog\_perc\_id\_r1 M.murinus % Identity  
450 marmoset\_ensembl\_gene Marmoset Ensembl Gene ID  
451 marmoset\_homolog\_ensembl\_peptide Marmoset Ensembl Protein ID  
452 marmoset\_chromosome Marmoset Chromosome  
453 marmoset\_chrom\_start Marmoset Chromosome Start (bp)  
454 marmoset\_chrom\_end Marmoset Chromosome End (bp)  
455 marmoset\_orthology\_type Homology Type  
456 marmoset\_homolog\_subtype Ancestor  
457 marmoset\_homolog\_dn dS  
458 marmoset\_homolog\_ds dN  
459 marmoset\_homolog\_perc\_id % Identity  
460 marmoset\_homolog\_perc\_id\_r1 Marmoset % Identity  
461 medaka\_ensembl\_gene Medaka Ensembl Gene ID  
462 medaka\_homolog\_ensembl\_peptide Medaka Ensembl Protein ID  
463 medaka\_chromosome Medaka Chromosome  
464 medaka\_chrom\_start Medaka Chromosome Start (bp)  
465 medaka\_chrom\_end Medaka Chromosome End (bp)  
466 medaka\_orthology\_type Homology Type  
467 medaka\_homolog\_subtype Ancestor  
468 medaka\_homolog\_dn dS  
469 medaka\_homolog\_ds dN  
470 medaka\_homolog\_perc\_id % Identity  
471 medaka\_homolog\_perc\_id\_r1 Medaka % Identity  
472 megabat\_ensembl\_gene Megabat Ensembl Gene ID  
473 megabat\_homolog\_ensembl\_peptide Megabat Ensembl Protein ID  
474 megabat\_chromosome Megabat Chromosome  
475 megabat\_chrom\_start Megabat Chromosome Start (bp)  
476 megabat\_chrom\_end Megabat Chromosome End (bp)  
477 megabat\_orthology\_type Homology Type  
478 megabat\_homolog\_subtype Ancestor  
479 megabat\_homolog\_dn dS  
480 megabat\_homolog\_ds dN  
481 megabat\_homolog\_perc\_id % Identity  
482 megabat\_homolog\_perc\_id\_r1 Megabat % Identity  
483 microbat\_ensembl\_gene Microbat Ensembl Gene ID  
484 microbat\_homolog\_ensembl\_peptide Microbat Ensembl Protein ID  
485 microbat\_chromosome Microbat Chromosome  
486 microbat\_chrom\_start Microbat Chromosome Start (bp)  
487 microbat\_chrom\_end Microbat Chromosome End (bp)  
488 microbat\_orthology\_type Homology Type  
489 microbat\_homolog\_subtype Ancestor  
490 microbat\_homolog\_dn dS  
491 microbat\_homolog\_ds dN  
492 microbat\_homolog\_perc\_id % Identity  
493 microbat\_homolog\_perc\_id\_r1 Microbat % Identity  
494 opossum\_ensembl\_gene Monodelphis domestica Ensembl Gene ID  
495 opossum\_homolog\_ensembl\_peptide Monodelphis domestica Ensembl
Protein ID  
496 opossum\_chromosome Monodelphis domestica Chromosome  
497 opossum\_chrom\_start Monodelphis domestica Chromosome Start (bp)  
498 opossum\_chrom\_end Monodelphis domestica Chromosome End (bp)  
499 opossum\_orthology\_type Homology Type  
500 opossum\_homolog\_subtype Ancestor  
501 opossum\_homolog\_dn dS  
502 opossum\_homolog\_ds dN  
503 opossum\_homolog\_perc\_id % Identity  
504 opossum\_homolog\_perc\_id\_r1 Monodelphis domestica % Identity  
505 mouse\_ensembl\_gene Mouse Ensembl Gene ID  
506 mouse\_homolog\_ensembl\_peptide Mouse Ensembl Protein ID  
507 mouse\_chromosome Mouse Chromosome  
508 mouse\_chrom\_start Mouse Chromosome Start (bp)  
509 mouse\_chrom\_end Mouse Chromosome End (bp)  
510 mouse\_orthology\_type Homology Type  
511 mouse\_homolog\_subtype Ancestor  
512 mouse\_homolog\_dn dS  
513 mouse\_homolog\_ds dN  
514 mouse\_homolog\_perc\_id % Identity  
515 mouse\_homolog\_perc\_id\_r1 Mouse % Identity  
516 orangutan\_ensembl\_gene Orangutan Ensembl Gene ID  
517 orangutan\_homolog\_ensembl\_peptide Orangutan Ensembl Protein ID  
518 orangutan\_chromosome Orangutan Chromosome  
519 orangutan\_chrom\_start Orangutan Chromosome Start (bp)  
520 orangutan\_chrom\_end Orangutan Chromosome End (bp)  
521 orangutan\_orthology\_type Homology Type  
522 orangutan\_homolog\_subtype Ancestor  
523 orangutan\_homolog\_dn dS  
524 orangutan\_homolog\_ds dN  
525 orangutan\_homolog\_perc\_id % Identity  
526 orangutan\_homolog\_perc\_id\_r1 Orangutan % Identity  
527 pig\_ensembl\_gene Pig Ensembl Gene ID  
528 pig\_homolog\_ensembl\_peptide Pig Ensembl Protein ID  
529 pig\_chromosome Pig Chromosome  
530 pig\_chrom\_start Pig Chromosome Start (bp)  
531 pig\_chrom\_end Pig Chromosome End (bp)  
532 pig\_orthology\_type Homology Type  
533 pig\_homolog\_subtype Ancestor  
534 pig\_homolog\_dn dS  
535 pig\_homolog\_ds dN  
536 pig\_homolog\_perc\_id % Identity  
537 pig\_homolog\_perc\_id\_r1 Pig % Identity  
538 pika\_ensembl\_gene Pika Ensembl Gene ID  
539 pika\_homolog\_ensembl\_peptide Pika Ensembl Protein ID  
540 pika\_chromosome Pika Chromosome  
541 pika\_chrom\_start Pika Chromosome Start (bp)  
542 pika\_chrom\_end Pika Chromosome End (bp)  
543 pika\_orthology\_type Homology Type  
544 pika\_homolog\_subtype Ancestor  
545 pika\_homolog\_dn dS  
546 pika\_homolog\_ds dN  
547 pika\_homolog\_perc\_id % Identity  
548 pika\_homolog\_perc\_id\_r1 Pika % Identity  
549 platypus\_ensembl\_gene Platypus Ensembl Gene ID  
550 platypus\_homolog\_ensembl\_peptide Platypus Ensembl Protein ID  
551 platypus\_chromosome Platypus Chromosome  
552 platypus\_chrom\_start Platypus Chromosome Start (bp)  
553 platypus\_chrom\_end Platypus Chromosome End (bp)  
554 platypus\_orthology\_type Homology Type  
555 platypus\_homolog\_subtype Ancestor  
556 platypus\_homolog\_dn dS  
557 platypus\_homolog\_ds dN  
558 platypus\_homolog\_perc\_id % Identity  
559 platypus\_homolog\_perc\_id\_r1 Platypus % Identity  
560 rabbit\_ensembl\_gene Rabbit Ensembl Gene ID  
561 rabbit\_homolog\_ensembl\_peptide Rabbit Ensembl Protein ID  
562 rabbit\_chromosome Rabbit Chromosome  
563 rabbit\_chrom\_start Rabbit Chromosome Start (bp)  
564 rabbit\_chrom\_end Rabbit Chromosome End (bp)  
565 rabbit\_orthology\_type Homology Type  
566 rabbit\_homolog\_subtype Ancestor  
567 rabbit\_homolog\_dn dS  
568 rabbit\_homolog\_ds dN  
569 rabbit\_homolog\_perc\_id % Identity  
570 rabbit\_homolog\_perc\_id\_r1 Rabbit % Identity  
571 rat\_ensembl\_gene Rat Ensembl Gene ID  
572 rat\_homolog\_ensembl\_peptide Rat Ensembl Protein ID  
573 rat\_chromosome Rat Chromosome  
574 rat\_chrom\_start Rat Chromosome Start (bp)  
575 rat\_chrom\_end Rat Chromosome End (bp)  
576 rat\_orthology\_type Homology Type  
577 rat\_homolog\_subtype Ancestor  
578 rat\_homolog\_dn dS  
579 rat\_homolog\_ds dN  
580 rat\_homolog\_perc\_id % Identity  
581 rat\_homolog\_perc\_id\_r1 Rat % Identity  
582 rhesus\_ensembl\_gene Rhesus Ensembl Gene ID  
583 rhesus\_homolog\_ensembl\_peptide Rhesus Ensembl Protein ID  
584 rhesus\_chromosome Rhesus Chromosome  
585 rhesus\_chrom\_start Rhesus Chromosome Start (bp)  
586 rhesus\_chrom\_end Rhesus Chromosome End (bp)  
587 rhesus\_orthology\_type Homology Type  
588 rhesus\_homolog\_subtype Ancestor  
589 rhesus\_homolog\_dn dS  
590 rhesus\_homolog\_ds dN  
591 rhesus\_homolog\_perc\_id % Identity  
592 rhesus\_homolog\_perc\_id\_r1 Rhesus % Identity  
593 pcapensis\_ensembl\_gene Rock Hyrax Ensembl Gene ID  
594 pcapensis\_homolog\_ensembl\_peptide Rock Hyrax Ensembl Protein ID  
595 pcapensis\_chromosome Rock Hyrax Chromosome  
596 pcapensis\_chrom\_start Rock Hyrax Chromosome Start (bp)  
597 pcapensis\_chrom\_end Rock Hyrax Chromosome End (bp)  
598 pcapensis\_orthology\_type Homology Type  
599 pcapensis\_homolog\_subtype Ancestor  
600 pcapensis\_homolog\_dn dS  
601 pcapensis\_homolog\_ds dN  
602 pcapensis\_homolog\_perc\_id % Identity  
603 pcapensis\_homolog\_perc\_id\_r1 Rock Hyrax % Identity  
604 sloth\_ensembl\_gene Sloth Ensembl Gene ID  
605 sloth\_homolog\_ensembl\_peptide Sloth Ensembl Protein ID  
606 sloth\_chromosome Sloth Chromosome  
607 sloth\_chrom\_start Sloth Chromosome Start (bp)  
608 sloth\_chrom\_end Sloth Chromosome End (bp)  
609 sloth\_orthology\_type Homology Type  
610 sloth\_homolog\_subtype Ancestor  
611 sloth\_homolog\_dn dS  
612 sloth\_homolog\_ds dN  
613 sloth\_homolog\_perc\_id % Identity  
614 sloth\_homolog\_perc\_id\_r1 Sloth % Identity  
615 squirrel\_ensembl\_gene Squirrel Ensembl Gene ID  
616 squirrel\_homolog\_ensembl\_peptide Squirrel Ensembl Protein ID  
617 squirrel\_chromosome Squirrel Chromosome  
618 squirrel\_chrom\_start Squirrel Chromosome Start (bp)  
619 squirrel\_chrom\_end Squirrel Chromosome End (bp)  
620 squirrel\_orthology\_type Homology Type  
621 squirrel\_homolog\_subtype Ancestor  
622 squirrel\_homolog\_dn dS  
623 squirrel\_homolog\_ds dN  
624 squirrel\_homolog\_perc\_id % Identity  
625 squirrel\_homolog\_perc\_id\_r1 Squirrel % Identity  
626 gaculeatus\_ensembl\_gene Stickleback Ensembl Gene ID  
627 gaculeatus\_homolog\_ensembl\_peptide Stickleback Ensembl Protein
ID  
628 gaculeatus\_chromosome Stickleback Chromosome  
629 gaculeatus\_chrom\_start Stickleback Chromosome Start (bp)  
630 gaculeatus\_chrom\_end Stickleback Chromosome End (bp)  
631 gaculeatus\_orthology\_type Homology Type  
632 gaculeatus\_homolog\_subtype Ancestor  
633 gaculeatus\_homolog\_dn dS  
634 gaculeatus\_homolog\_ds dN  
635 gaculeatus\_homolog\_perc\_id % Identity  
636 gaculeatus\_homolog\_perc\_id\_r1 Stickleback % Identity  
637 tarsier\_ensembl\_gene Tarsier Ensembl Gene ID  
638 tarsier\_homolog\_ensembl\_peptide Tarsier Ensembl Protein ID  
639 tarsier\_chromosome Tarsier Chromosome  
640 tarsier\_chrom\_start Tarsier Chromosome Start (bp)  
641 tarsier\_chrom\_end Tarsier Chromosome End (bp)  
642 tarsier\_orthology\_type Homology Type  
643 tarsier\_homolog\_subtype Ancestor  
644 tarsier\_homolog\_dn dS  
645 tarsier\_homolog\_ds dN  
646 tarsier\_homolog\_perc\_id % Identity  
647 tarsier\_homolog\_perc\_id\_r1 Tarsier % Identity  
648 tenrec\_ensembl\_gene Tenrec Ensembl Gene ID  
649 tenrec\_homolog\_ensembl\_peptide Tenrec Ensembl Protein ID  
650 tenrec\_chromosome Tenrec Chromosome  
651 tenrec\_chrom\_start Tenrec Chromosome Start (bp)  
652 tenrec\_chrom\_end Tenrec Chromosome End (bp)  
653 tenrec\_orthology\_type Homology Type  
654 tenrec\_homolog\_subtype Ancestor  
655 tenrec\_homolog\_dn dS  
656 tenrec\_homolog\_ds dN  
657 tenrec\_homolog\_perc\_id % Identity  
658 tenrec\_homolog\_perc\_id\_r1 Tenrec % Identity  
659 tetraodon\_ensembl\_gene Tetraodon Ensembl Gene ID  
660 tetraodon\_homolog\_ensembl\_peptide Tetraodon Ensembl Protein ID  
661 tetraodon\_chromosome Tetraodon Chromosome  
662 tetraodon\_chrom\_start Tetraodon Chromosome Start (bp)  
663 tetraodon\_chrom\_end Tetraodon Chromosome End (bp)  
664 tetraodon\_orthology\_type Homology Type  
665 tetraodon\_homolog\_subtype Ancestor  
666 tetraodon\_homolog\_dn dS  
667 tetraodon\_homolog\_ds dN  
668 tetraodon\_homolog\_perc\_id % Identity  
669 tetraodon\_homolog\_perc\_id\_r1 Tetraodon % Identity  
670 tree\_shrew\_ensembl\_gene Tree Shrew Ensembl Gene ID  
671 tree\_shrew\_homolog\_ensembl\_peptide Tree Shrew Ensembl Protein
ID  
672 tree\_shrew\_chromosome Tree Shrew Chromosome  
673 tree\_shrew\_chrom\_start Tree Shrew Chromosome Start (bp)  
674 tree\_shrew\_chrom\_end Tree Shrew Chromosome End (bp)  
675 tree\_shrew\_orthology\_type Homology Type  
676 tree\_shrew\_homolog\_subtype Ancestor  
677 tree\_shrew\_homolog\_dn dS  
678 tree\_shrew\_homolog\_ds dN  
679 tree\_shrew\_homolog\_perc\_id % Identity  
680 tree\_shrew\_homolog\_perc\_id\_r1 Tree Shrew % Identity  
681 wallaby\_ensembl\_gene Wallaby Ensembl Gene ID  
682 wallaby\_homolog\_ensembl\_peptide Wallaby Ensembl Protein ID  
683 wallaby\_chromosome Wallaby Chromosome  
684 wallaby\_chrom\_start Wallaby Chromosome Start (bp)  
685 wallaby\_chrom\_end Wallaby Chromosome End (bp)  
686 wallaby\_orthology\_type Homology Type  
687 wallaby\_homolog\_subtype Ancestor  
688 wallaby\_homolog\_dn dS  
689 wallaby\_homolog\_ds dN  
690 wallaby\_homolog\_perc\_id % Identity  
691 wallaby\_homolog\_perc\_id\_r1 Wallaby % Identity  
692 yeast\_ensembl\_gene Yeast Ensembl Gene ID  
693 yeast\_homolog\_ensembl\_peptide Yeast Ensembl Protein ID  
694 yeast\_chromosome Yeast Chromosome  
695 yeast\_chrom\_start Yeast Chromosome Start (bp)  
696 yeast\_chrom\_end Yeast Chromosome End (bp)  
697 yeast\_orthology\_type Homology Type  
698 yeast\_homolog\_subtype Ancestor  
699 yeast\_homolog\_dn dS  
700 yeast\_homolog\_ds dN  
701 yeast\_homolog\_perc\_id % Identity  
702 yeast\_homolog\_perc\_id\_r1 Yeast % Identity  
703 zebra\_finch\_ensembl\_gene Zebra Finch Ensembl Gene ID  
704 zebra\_finch\_homolog\_ensembl\_peptide Zebra Finch Ensembl Protein
ID  
705 zebra\_finch\_chromosome Zebra Finch Chromosome  
706 zebra\_finch\_chrom\_start Zebra Finch Chromosome Start (bp)  
707 zebra\_finch\_chrom\_end Zebra Finch Chromosome End (bp)  
708 zebra\_finch\_orthology\_type Homology Type  
709 zebra\_finch\_homolog\_subtype Ancestor  
710 zebra\_finch\_homolog\_dn dS  
711 zebra\_finch\_homolog\_ds dN  
712 zebra\_finch\_homolog\_perc\_id % Identity  
713 zebra\_finch\_homolog\_perc\_id\_r1 Zebra Finch % Identity  
714 zebrafish\_ensembl\_gene Zebrafish Ensembl Gene ID  
715 zebrafish\_homolog\_ensembl\_peptide Zebrafish Ensembl Protein ID  
716 zebrafish\_chromosome Zebrafish Chromosome  
717 zebrafish\_chrom\_start Zebrafish Chromosome Start (bp)  
718 zebrafish\_chrom\_end Zebrafish Chromosome End (bp)  
719 zebrafish\_orthology\_type Homology Type  
720 zebrafish\_homolog\_subtype Ancestor  
721 zebrafish\_homolog\_dn dS  
722 zebrafish\_homolog\_ds dN  
723 zebrafish\_homolog\_perc\_id % Identity  
724 zebrafish\_homolog\_perc\_id\_r1 Zebrafish % Identity  
725 inter\_paralog\_alpaca\_ensembl\_gene Alpaca Ensembl Gene ID  
726 inter\_paralog\_alpaca\_inter\_paralog\_ensembl\_peptide Alpaca
Ensembl Protein ID  
727 inter\_paralog\_alpaca\_chromosome Alpaca Chromosome  
728 inter\_paralog\_alpaca\_chrom\_start Alpaca Chromosome Start (bp)  
729 inter\_paralog\_alpaca\_chrom\_end Alpaca Chromosome End (bp)  
730 inter\_paralog\_alpaca\_orthology\_type Homology Type  
731 alpaca\_inter\_paralog\_subtype Ancestor  
732 alpaca\_inter\_paralog\_dn dS  
733 alpaca\_inter\_paralog\_ds dN  
734 alpaca\_inter\_paralog\_perc\_id % Identity  
735 alpaca\_inter\_paralog\_perc\_id\_r1 Alpaca % Identity  
736 inter\_paralog\_anole\_lizard\_ensembl\_gene Anole Lizard Ensembl
Gene ID  
737 inter\_paralog\_anole\_lizard\_inter\_paralog\_ensembl\_peptide
Anole Lizard Ensembl Protein ID  
738 inter\_paralog\_anole\_lizard\_chromosome Anole Lizard Chromosome  
739 inter\_paralog\_anole\_lizard\_chrom\_start Anole Lizard Chromosome
Start (bp)  
740 inter\_paralog\_anole\_lizard\_chrom\_end Anole Lizard Chromosome
End (bp)  
741 inter\_paralog\_anole\_lizard\_orthology\_type Homology Type  
742 anole\_lizard\_inter\_paralog\_subtype Ancestor  
743 anole\_lizard\_inter\_paralog\_dn dS  
744 anole\_lizard\_inter\_paralog\_ds dN  
745 anole\_lizard\_inter\_paralog\_perc\_id % Identity  
746 anole\_lizard\_inter\_paralog\_perc\_id\_r1 Anole Lizard %
Identity  
747 inter\_paralog\_armadillo\_ensembl\_gene Armadillo Ensembl Gene ID  
748 inter\_paralog\_armadillo\_inter\_paralog\_ensembl\_peptide
Armadillo Ensembl Protein ID  
749 inter\_paralog\_armadillo\_chromosome Armadillo Chromosome  
750 inter\_paralog\_armadillo\_chrom\_start Armadillo Chromosome Start
(bp)  
751 inter\_paralog\_armadillo\_chrom\_end Armadillo Chromosome End
(bp)  
752 inter\_paralog\_armadillo\_orthology\_type Homology Type  
753 armadillo\_inter\_paralog\_subtype Ancestor  
754 armadillo\_inter\_paralog\_dn dS  
755 armadillo\_inter\_paralog\_ds dN  
756 armadillo\_inter\_paralog\_perc\_id % Identity  
757 armadillo\_inter\_paralog\_perc\_id\_r1 Armadillo % Identity  
758 inter\_paralog\_bushbaby\_ensembl\_gene Bushbaby Ensembl Gene ID  
759 inter\_paralog\_bushbaby\_inter\_paralog\_ensembl\_peptide Bushbaby
Ensembl Protein ID  
760 inter\_paralog\_bushbaby\_chromosome Bushbaby Chromosome  
761 inter\_paralog\_bushbaby\_chrom\_start Bushbaby Chromosome Start
(bp)  
762 inter\_paralog\_bushbaby\_chrom\_end Bushbaby Chromosome End (bp)  
763 inter\_paralog\_bushbaby\_orthology\_type Homology Type  
764 bushbaby\_inter\_paralog\_subtype Ancestor  
765 bushbaby\_inter\_paralog\_dn dS  
766 bushbaby\_inter\_paralog\_ds dN  
767 bushbaby\_inter\_paralog\_perc\_id % Identity  
768 bushbaby\_inter\_paralog\_perc\_id\_r1 Bushbaby % Identity  
769 inter\_paralog\_cat\_ensembl\_gene Cat Ensembl Gene ID  
770 inter\_paralog\_cat\_inter\_paralog\_ensembl\_peptide Cat Ensembl
Protein ID  
771 inter\_paralog\_cat\_chromosome Cat Chromosome  
772 inter\_paralog\_cat\_chrom\_start Cat Chromosome Start (bp)  
773 inter\_paralog\_cat\_chrom\_end Cat Chromosome End (bp)  
774 inter\_paralog\_cat\_orthology\_type Homology Type  
775 cat\_inter\_paralog\_subtype Ancestor  
776 cat\_inter\_paralog\_dn dS  
777 cat\_inter\_paralog\_ds dN  
778 cat\_inter\_paralog\_perc\_id % Identity  
779 cat\_inter\_paralog\_perc\_id\_r1 Cat % Identity  
780 inter\_paralog\_chicken\_ensembl\_gene Chicken Ensembl Gene ID  
781 inter\_paralog\_chicken\_inter\_paralog\_ensembl\_peptide Chicken
Ensembl Protein ID  
782 inter\_paralog\_chicken\_chromosome Chicken Chromosome  
783 inter\_paralog\_chicken\_chrom\_start Chicken Chromosome Start
(bp)  
784 inter\_paralog\_chicken\_chrom\_end Chicken Chromosome End (bp)  
785 inter\_paralog\_chicken\_orthology\_type Homology Type  
786 chicken\_inter\_paralog\_subtype Ancestor  
787 chicken\_inter\_paralog\_dn dS  
788 chicken\_inter\_paralog\_ds dN  
789 chicken\_inter\_paralog\_perc\_id % Identity  
790 chicken\_inter\_paralog\_perc\_id\_r1 Chicken % Identity  
791 inter\_paralog\_chimp\_ensembl\_gene Chimp Ensembl Gene ID  
792 inter\_paralog\_chimp\_inter\_paralog\_ensembl\_peptide Chimp
Ensembl Protein ID  
793 inter\_paralog\_chimp\_chromosome Chimp Chromosome  
794 inter\_paralog\_chimp\_chrom\_start Chimp Chromosome Start (bp)  
795 inter\_paralog\_chimp\_chrom\_end Chimp Chromosome End (bp)  
796 inter\_paralog\_chimp\_orthology\_type Homology Type  
797 chimp\_inter\_paralog\_subtype Ancestor  
798 chimp\_inter\_paralog\_dn dS  
799 chimp\_inter\_paralog\_ds dN  
800 chimp\_inter\_paralog\_perc\_id % Identity  
801 chimp\_inter\_paralog\_perc\_id\_r1 Chimp % Identity  
802 inter\_paralog\_ciona\_intestinalis\_ensembl\_gene Ciona
intestinalis Ensembl Gene ID  
803
inter\_paralog\_ciona\_intestinalis\_inter\_paralog\_ensembl\_peptide
Ciona intestinalis Ensembl Protein ID  
804 inter\_paralog\_ciona\_intestinalis\_chromosome Ciona intestinalis
Chromosome  
805 inter\_paralog\_ciona\_intestinalis\_chrom\_start Ciona intestinalis
Chromosome Start (bp)  
806 inter\_paralog\_ciona\_intestinalis\_chrom\_end Ciona intestinalis
Chromosome End (bp)  
807 inter\_paralog\_ciona\_intestinalis\_orthology\_type Homology Type  
808 ciona\_intestinalis\_inter\_paralog\_subtype Ancestor  
809 ciona\_intestinalis\_inter\_paralog\_dn dS  
810 ciona\_intestinalis\_inter\_paralog\_ds dN  
811 ciona\_intestinalis\_inter\_paralog\_perc\_id % Identity  
812 ciona\_intestinalis\_inter\_paralog\_perc\_id\_r1 Ciona intestinalis
% Identity  
813 inter\_paralog\_ciona\_savigngi\_ensembl\_gene Ciona savigngi
Ensembl Gene ID  
814 inter\_paralog\_ciona\_savigngi\_inter\_paralog\_ensembl\_peptide
Ciona savigngi Ensembl Protein ID  
815 inter\_paralog\_ciona\_savigngi\_chromosome Ciona savigngi
Chromosome  
816 inter\_paralog\_ciona\_savigngi\_chrom\_start Ciona savigngi
Chromosome Start (bp)  
817 inter\_paralog\_ciona\_savigngi\_chrom\_end Ciona savigngi
Chromosome End (bp)  
818 inter\_paralog\_ciona\_savigngi\_orthology\_type Homology Type  
819 ciona\_savigngi\_inter\_paralog\_subtype Ancestor  
820 ciona\_savigngi\_inter\_paralog\_dn dS  
821 ciona\_savigngi\_inter\_paralog\_ds dN  
822 ciona\_savigngi\_inter\_paralog\_perc\_id % Identity  
823 ciona\_savigngi\_inter\_paralog\_perc\_id\_r1 Ciona savigngi %
Identity  
824 inter\_paralog\_common\_shrew\_ensembl\_gene Common Shrew Ensembl
Gene ID  
825 inter\_paralog\_common\_shrew\_inter\_paralog\_ensembl\_peptide
Common Shrew Ensembl Protein ID  
826 inter\_paralog\_common\_shrew\_chromosome Common Shrew Chromosome  
827 inter\_paralog\_common\_shrew\_chrom\_start Common Shrew Chromosome
Start (bp)  
828 inter\_paralog\_common\_shrew\_chrom\_end Common Shrew Chromosome
End (bp)  
829 inter\_paralog\_common\_shrew\_orthology\_type Homology Type  
830 common\_shrew\_inter\_paralog\_subtype Ancestor  
831 common\_shrew\_inter\_paralog\_dn dS  
832 common\_shrew\_inter\_paralog\_ds dN  
833 common\_shrew\_inter\_paralog\_perc\_id % Identity  
834 common\_shrew\_inter\_paralog\_perc\_id\_r1 Common Shrew %
Identity  
835 inter\_paralog\_cow\_ensembl\_gene Cow Ensembl Gene ID  
836 inter\_paralog\_cow\_inter\_paralog\_ensembl\_peptide Cow Ensembl
Protein ID  
837 inter\_paralog\_cow\_chromosome Cow Chromosome  
838 inter\_paralog\_cow\_chrom\_start Cow Chromosome Start (bp)  
839 inter\_paralog\_cow\_chrom\_end Cow Chromosome End (bp)  
840 inter\_paralog\_cow\_orthology\_type Homology Type  
841 cow\_inter\_paralog\_subtype Ancestor  
842 cow\_inter\_paralog\_dn dS  
843 cow\_inter\_paralog\_ds dN  
844 cow\_inter\_paralog\_perc\_id % Identity  
845 cow\_inter\_paralog\_perc\_id\_r1 Cow % Identity  
846 inter\_paralog\_dog\_ensembl\_gene Dog Ensembl Gene ID  
847 inter\_paralog\_dog\_inter\_paralog\_ensembl\_peptide Dog Ensembl
Protein ID  
848 inter\_paralog\_dog\_chromosome Dog Chromosome  
849 inter\_paralog\_dog\_chrom\_start Dog Chromosome Start (bp)  
850 inter\_paralog\_dog\_chrom\_end Dog Chromosome End (bp)  
851 inter\_paralog\_dog\_orthology\_type Homology Type  
852 dog\_inter\_paralog\_subtype Ancestor  
853 dog\_inter\_paralog\_dn dS  
854 dog\_inter\_paralog\_ds dN  
855 dog\_inter\_paralog\_perc\_id % Identity  
856 dog\_inter\_paralog\_perc\_id\_r1 Dog % Identity  
857 inter\_paralog\_dolphin\_ensembl\_gene Dolphin Ensembl Gene ID  
858 inter\_paralog\_dolphin\_inter\_paralog\_ensembl\_peptide Dolphin
Ensembl Protein ID  
859 inter\_paralog\_dolphin\_chromosome Dolphin Chromosome  
860 inter\_paralog\_dolphin\_chrom\_start Dolphin Chromosome Start
(bp)  
861 inter\_paralog\_dolphin\_chrom\_end Dolphin Chromosome End (bp)  
862 inter\_paralog\_dolphin\_orthology\_type Homology Type  
863 dolphin\_inter\_paralog\_subtype Ancestor  
864 dolphin\_inter\_paralog\_dn dS  
865 dolphin\_inter\_paralog\_ds dN  
866 dolphin\_inter\_paralog\_perc\_id % Identity  
867 dolphin\_inter\_paralog\_perc\_id\_r1 Dolphin % Identity  
868 inter\_paralog\_drosophila\_ensembl\_gene Drosophila Ensembl Gene
ID  
869 inter\_paralog\_drosophila\_inter\_paralog\_ensembl\_peptide
Drosophila Ensembl Protein ID  
870 inter\_paralog\_drosophila\_chromosome Drosophila Chromosome  
871 inter\_paralog\_drosophila\_chrom\_start Drosophila Chromosome Start
(bp)  
872 inter\_paralog\_drosophila\_chrom\_end Drosophila Chromosome End
(bp)  
873 inter\_paralog\_drosophila\_orthology\_type Homology Type  
874 drosophila\_inter\_paralog\_subtype Ancestor  
875 drosophila\_inter\_paralog\_dn dS  
876 drosophila\_inter\_paralog\_ds dN  
877 drosophila\_inter\_paralog\_perc\_id % Identity  
878 drosophila\_inter\_paralog\_perc\_id\_r1 Drosophila % Identity  
879 inter\_paralog\_elegans\_ensembl\_gene Elegans Ensembl Gene ID  
880 inter\_paralog\_elegans\_inter\_paralog\_ensembl\_peptide Elegans
Ensembl Protein ID  
881 inter\_paralog\_elegans\_chromosome Elegans Chromosome  
882 inter\_paralog\_elegans\_chrom\_start Elegans Chromosome Start
(bp)  
883 inter\_paralog\_elegans\_chrom\_end Elegans Chromosome End (bp)  
884 inter\_paralog\_elegans\_orthology\_type Homology Type  
885 elegans\_inter\_paralog\_subtype Ancestor  
886 elegans\_inter\_paralog\_dn dS  
887 elegans\_inter\_paralog\_ds dN  
888 elegans\_inter\_paralog\_perc\_id % Identity  
889 elegans\_inter\_paralog\_perc\_id\_r1 Elegans % Identity  
890 inter\_paralog\_elephant\_ensembl\_gene Elephant Ensembl Gene ID  
891 inter\_paralog\_elephant\_inter\_paralog\_ensembl\_peptide Elephant
Ensembl Protein ID  
892 inter\_paralog\_elephant\_chromosome Elephant Chromosome  
893 inter\_paralog\_elephant\_chrom\_start Elephant Chromosome Start
(bp)  
894 inter\_paralog\_elephant\_chrom\_end Elephant Chromosome End (bp)  
895 inter\_paralog\_elephant\_orthology\_type Homology Type  
896 elephant\_inter\_paralog\_subtype Ancestor  
897 elephant\_inter\_paralog\_dn dS  
898 elephant\_inter\_paralog\_ds dN  
899 elephant\_inter\_paralog\_perc\_id % Identity  
900 elephant\_inter\_paralog\_perc\_id\_r1 Elephant % Identity  
901 inter\_paralog\_xenopus\_ensembl\_gene Frog Ensembl Gene ID  
902 inter\_paralog\_xenopus\_inter\_paralog\_ensembl\_peptide Frog
Ensembl Protein ID  
903 inter\_paralog\_xenopus\_chromosome Frog Chromosome  
904 inter\_paralog\_xenopus\_chrom\_start Frog Chromosome Start (bp)  
905 inter\_paralog\_xenopus\_chrom\_end Frog Chromosome End (bp)  
906 inter\_paralog\_xenopus\_orthology\_type Homology Type  
907 xenopus\_inter\_paralog\_subtype Ancestor  
908 xenopus\_inter\_paralog\_dn dS  
909 xenopus\_inter\_paralog\_ds dN  
910 xenopus\_inter\_paralog\_perc\_id % Identity  
911 xenopus\_inter\_paralog\_perc\_id\_r1 Frog % Identity  
912 inter\_paralog\_fugu\_ensembl\_gene Fugu Ensembl Gene ID  
913 inter\_paralog\_fugu\_inter\_paralog\_ensembl\_peptide Fugu Ensembl
Protein ID  
914 inter\_paralog\_fugu\_chromosome Fugu Chromosome  
915 inter\_paralog\_fugu\_chrom\_start Fugu Chromosome Start (bp)  
916 inter\_paralog\_fugu\_chrom\_end Fugu Chromosome End (bp)  
917 inter\_paralog\_fugu\_orthology\_type Homology Type  
918 fugu\_inter\_paralog\_subtype Ancestor  
919 fugu\_inter\_paralog\_dn dS  
920 fugu\_inter\_paralog\_ds dN  
921 fugu\_inter\_paralog\_perc\_id % Identity  
922 fugu\_inter\_paralog\_perc\_id\_r1 Fugu % Identity  
923 inter\_paralog\_gorilla\_ensembl\_gene Gorilla Ensembl Gene ID  
924 inter\_paralog\_gorilla\_inter\_paralog\_ensembl\_peptide Gorilla
Ensembl Protein ID  
925 inter\_paralog\_gorilla\_chromosome Gorilla Chromosome  
926 inter\_paralog\_gorilla\_chrom\_start Gorilla Chromosome Start
(bp)  
927 inter\_paralog\_gorilla\_chrom\_end Gorilla Chromosome End (bp)  
928 inter\_paralog\_gorilla\_orthology\_type Homology Type  
929 gorilla\_inter\_paralog\_subtype Ancestor  
930 gorilla\_inter\_paralog\_dn dS  
931 gorilla\_inter\_paralog\_ds dN  
932 gorilla\_inter\_paralog\_perc\_id % Identity  
933 gorilla\_inter\_paralog\_perc\_id\_r1 Gorilla % Identity  
934 inter\_paralog\_guineapig\_ensembl\_gene Guinea Pig Ensembl Gene
ID  
935 inter\_paralog\_guineapig\_inter\_paralog\_ensembl\_peptide Guinea
Pig Ensembl Protein ID  
936 inter\_paralog\_guineapig\_chromosome Guinea Pig Chromosome  
937 inter\_paralog\_guineapig\_chrom\_start Guinea Pig Chromosome Start
(bp)  
938 inter\_paralog\_guineapig\_chrom\_end Guinea Pig Chromosome End
(bp)  
939 inter\_paralog\_guineapig\_orthology\_type Homology Type  
940 guineapig\_inter\_paralog\_subtype Ancestor  
941 guineapig\_inter\_paralog\_dn dS  
942 guineapig\_inter\_paralog\_ds dN  
943 guineapig\_inter\_paralog\_perc\_id % Identity  
944 guineapig\_inter\_paralog\_perc\_id\_r1 Guinea Pig % Identity  
945 inter\_paralog\_hedgehog\_ensembl\_gene Hedgehog Ensembl Gene ID  
946 inter\_paralog\_hedgehog\_inter\_paralog\_ensembl\_peptide Hedgehog
Ensembl Protein ID  
947 inter\_paralog\_hedgehog\_chromosome Hedgehog Chromosome  
948 inter\_paralog\_hedgehog\_chrom\_start Hedgehog Chromosome Start
(bp)  
949 inter\_paralog\_hedgehog\_chrom\_end Hedgehog Chromosome End (bp)  
950 inter\_paralog\_hedgehog\_orthology\_type Homology Type  
951 hedgehog\_inter\_paralog\_subtype Ancestor  
952 hedgehog\_inter\_paralog\_dn dS  
953 hedgehog\_inter\_paralog\_ds dN  
954 hedgehog\_inter\_paralog\_perc\_id % Identity  
955 hedgehog\_inter\_paralog\_perc\_id\_r1 Hedgehog % Identity  
956 inter\_paralog\_horse\_ensembl\_gene Horse Ensembl Gene ID  
957 inter\_paralog\_horse\_inter\_paralog\_ensembl\_peptide Horse
Ensembl Protein ID  
958 inter\_paralog\_horse\_chromosome Horse Chromosome  
959 inter\_paralog\_horse\_chrom\_start Horse Chromosome Start (bp)  
960 inter\_paralog\_horse\_chrom\_end Horse Chromosome End (bp)  
961 inter\_paralog\_horse\_orthology\_type Homology Type  
962 horse\_inter\_paralog\_subtype Ancestor  
963 horse\_inter\_paralog\_dn dS  
964 horse\_inter\_paralog\_ds dN  
965 horse\_inter\_paralog\_perc\_id % Identity  
966 horse\_inter\_paralog\_perc\_id\_r1 Horse % Identity  
967 inter\_paralog\_dordii\_ensembl\_gene Kangaroo Ensembl Gene ID  
968 inter\_paralog\_dordii\_inter\_paralog\_ensembl\_peptide Kangaroo
Ensembl Protein ID  
969 inter\_paralog\_dordii\_chromosome Kangaroo Chromosome  
970 inter\_paralog\_dordii\_chrom\_start Kangaroo Chromosome Start
(bp)  
971 inter\_paralog\_dordii\_chrom\_end Kangaroo Chromosome End (bp)  
972 inter\_paralog\_dordii\_orthology\_type Homology Type  
973 dordii\_inter\_paralog\_subtype Ancestor  
974 dordii\_inter\_paralog\_dn dS  
975 dordii\_inter\_paralog\_ds dN  
976 dordii\_inter\_paralog\_perc\_id % Identity  
977 dordii\_inter\_paralog\_perc\_id\_r1 Kangaroo % Identity  
978 inter\_paralog\_mmur\_ensembl\_gene M.murinus Ensembl Gene ID  
979 inter\_paralog\_mmur\_inter\_paralog\_ensembl\_peptide M.murinus
Ensembl Protein ID  
980 inter\_paralog\_mmur\_chromosome M.murinus Chromosome  
981 inter\_paralog\_mmur\_chrom\_start M.murinus Chromosome Start (bp)  
982 inter\_paralog\_mmur\_chrom\_end M.murinus Chromosome End (bp)  
983 inter\_paralog\_mmur\_orthology\_type Homology Type  
984 mmur\_inter\_paralog\_subtype Ancestor  
985 mmur\_inter\_paralog\_dn dS  
986 mmur\_inter\_paralog\_ds dN  
987 mmur\_inter\_paralog\_perc\_id % Identity  
988 mmur\_inter\_paralog\_perc\_id\_r1 M.murinus % Identity  
989 inter\_paralog\_marmoset\_ensembl\_gene Marmoset Ensembl Gene ID  
990 inter\_paralog\_marmoset\_inter\_paralog\_ensembl\_peptide Marmoset
Ensembl Protein ID  
991 inter\_paralog\_marmoset\_chromosome Marmoset Chromosome  
992 inter\_paralog\_marmoset\_chrom\_start Marmoset Chromosome Start
(bp)  
993 inter\_paralog\_marmoset\_chrom\_end Marmoset Chromosome End (bp)  
994 inter\_paralog\_marmoset\_orthology\_type Homology Type  
995 marmoset\_inter\_paralog\_subtype Ancestor  
996 marmoset\_inter\_paralog\_dn dS  
997 marmoset\_inter\_paralog\_ds dN  
998 marmoset\_inter\_paralog\_perc\_id % Identity  
999 marmoset\_inter\_paralog\_perc\_id\_r1 Marmoset % Identity  
1000 inter\_paralog\_medaka\_ensembl\_gene Medaka Ensembl Gene ID  
1001 inter\_paralog\_medaka\_inter\_paralog\_ensembl\_peptide Medaka
Ensembl Protein ID  
1002 inter\_paralog\_medaka\_chromosome Medaka Chromosome  
1003 inter\_paralog\_medaka\_chrom\_start Medaka Chromosome Start (bp)  
1004 inter\_paralog\_medaka\_chrom\_end Medaka Chromosome End (bp)  
1005 inter\_paralog\_medaka\_orthology\_type Homology Type  
1006 medaka\_inter\_paralog\_subtype Ancestor  
1007 medaka\_inter\_paralog\_dn dS  
1008 medaka\_inter\_paralog\_ds dN  
1009 medaka\_inter\_paralog\_perc\_id % Identity  
1010 medaka\_inter\_paralog\_perc\_id\_r1 Medaka % Identity  
1011 inter\_paralog\_megabat\_ensembl\_gene Megabat Ensembl Gene ID  
1012 inter\_paralog\_megabat\_inter\_paralog\_ensembl\_peptide Megabat
Ensembl Protein ID  
1013 inter\_paralog\_megabat\_chromosome Megabat Chromosome  
1014 inter\_paralog\_megabat\_chrom\_start Megabat Chromosome Start
(bp)  
1015 inter\_paralog\_megabat\_chrom\_end Megabat Chromosome End (bp)  
1016 inter\_paralog\_megabat\_orthology\_type Homology Type  
1017 megabat\_inter\_paralog\_subtype Ancestor  
1018 megabat\_inter\_paralog\_dn dS  
1019 megabat\_inter\_paralog\_ds dN  
1020 megabat\_inter\_paralog\_perc\_id % Identity  
1021 megabat\_inter\_paralog\_perc\_id\_r1 Megabat % Identity  
1022 inter\_paralog\_microbat\_ensembl\_gene Microbat Ensembl Gene ID  
1023 inter\_paralog\_microbat\_inter\_paralog\_ensembl\_peptide Microbat
Ensembl Protein ID  
1024 inter\_paralog\_microbat\_chromosome Microbat Chromosome  
1025 inter\_paralog\_microbat\_chrom\_start Microbat Chromosome Start
(bp)  
1026 inter\_paralog\_microbat\_chrom\_end Microbat Chromosome End (bp)  
1027 inter\_paralog\_microbat\_orthology\_type Homology Type  
1028 microbat\_inter\_paralog\_subtype Ancestor  
1029 microbat\_inter\_paralog\_dn dS  
1030 microbat\_inter\_paralog\_ds dN  
1031 microbat\_inter\_paralog\_perc\_id % Identity  
1032 microbat\_inter\_paralog\_perc\_id\_r1 Microbat % Identity  
1033 inter\_paralog\_opossum\_ensembl\_gene Monodelphis domestica
Ensembl Gene ID  
1034 inter\_paralog\_opossum\_inter\_paralog\_ensembl\_peptide
Monodelphis domestica Ensembl Protein ID  
1035 inter\_paralog\_opossum\_chromosome Monodelphis domestica
Chromosome  
1036 inter\_paralog\_opossum\_chrom\_start Monodelphis domestica
Chromosome Start (bp)  
1037 inter\_paralog\_opossum\_chrom\_end Monodelphis domestica
Chromosome End (bp)  
1038 inter\_paralog\_opossum\_orthology\_type Homology Type  
1039 opossum\_inter\_paralog\_subtype Ancestor  
1040 opossum\_inter\_paralog\_dn dS  
1041 opossum\_inter\_paralog\_ds dN  
1042 opossum\_inter\_paralog\_perc\_id % Identity  
1043 opossum\_inter\_paralog\_perc\_id\_r1 Monodelphis domestica %
Identity  
1044 inter\_paralog\_mouse\_ensembl\_gene Mouse Ensembl Gene ID  
1045 inter\_paralog\_mouse\_inter\_paralog\_ensembl\_peptide Mouse
Ensembl Protein ID  
1046 inter\_paralog\_mouse\_chromosome Mouse Chromosome  
1047 inter\_paralog\_mouse\_chrom\_start Mouse Chromosome Start (bp)  
1048 inter\_paralog\_mouse\_chrom\_end Mouse Chromosome End (bp)  
1049 inter\_paralog\_mouse\_orthology\_type Homology Type  
1050 mouse\_inter\_paralog\_subtype Ancestor  
1051 mouse\_inter\_paralog\_dn dS  
1052 mouse\_inter\_paralog\_ds dN  
1053 mouse\_inter\_paralog\_perc\_id % Identity  
1054 mouse\_inter\_paralog\_perc\_id\_r1 Mouse % Identity  
1055 inter\_paralog\_orangutan\_ensembl\_gene Orangutan Ensembl Gene
ID  
1056 inter\_paralog\_orangutan\_inter\_paralog\_ensembl\_peptide
Orangutan Ensembl Protein ID  
1057 inter\_paralog\_orangutan\_chromosome Orangutan Chromosome  
1058 inter\_paralog\_orangutan\_chrom\_start Orangutan Chromosome Start
(bp)  
1059 inter\_paralog\_orangutan\_chrom\_end Orangutan Chromosome End
(bp)  
1060 inter\_paralog\_orangutan\_orthology\_type Homology Type  
1061 orangutan\_inter\_paralog\_subtype Ancestor  
1062 orangutan\_inter\_paralog\_dn dS  
1063 orangutan\_inter\_paralog\_ds dN  
1064 orangutan\_inter\_paralog\_perc\_id % Identity  
1065 orangutan\_inter\_paralog\_perc\_id\_r1 Orangutan % Identity  
1066 inter\_paralog\_pig\_ensembl\_gene Pig Ensembl Gene ID  
1067 inter\_paralog\_pig\_inter\_paralog\_ensembl\_peptide Pig Ensembl
Protein ID  
1068 inter\_paralog\_pig\_chromosome Pig Chromosome  
1069 inter\_paralog\_pig\_chrom\_start Pig Chromosome Start (bp)  
1070 inter\_paralog\_pig\_chrom\_end Pig Chromosome End (bp)  
1071 inter\_paralog\_pig\_orthology\_type Homology Type  
1072 pig\_inter\_paralog\_subtype Ancestor  
1073 pig\_inter\_paralog\_dn dS  
1074 pig\_inter\_paralog\_ds dN  
1075 pig\_inter\_paralog\_perc\_id % Identity  
1076 pig\_inter\_paralog\_perc\_id\_r1 Pig % Identity  
1077 inter\_paralog\_pika\_ensembl\_gene Pika Ensembl Gene ID  
1078 inter\_paralog\_pika\_inter\_paralog\_ensembl\_peptide Pika Ensembl
Protein ID  
1079 inter\_paralog\_pika\_chromosome Pika Chromosome  
1080 inter\_paralog\_pika\_chrom\_start Pika Chromosome Start (bp)  
1081 inter\_paralog\_pika\_chrom\_end Pika Chromosome End (bp)  
1082 inter\_paralog\_pika\_orthology\_type Homology Type  
1083 pika\_inter\_paralog\_subtype Ancestor  
1084 pika\_inter\_paralog\_dn dS  
1085 pika\_inter\_paralog\_ds dN  
1086 pika\_inter\_paralog\_perc\_id % Identity  
1087 pika\_inter\_paralog\_perc\_id\_r1 Pika % Identity  
1088 inter\_paralog\_platypus\_ensembl\_gene Platypus Ensembl Gene ID  
1089 inter\_paralog\_platypus\_inter\_paralog\_ensembl\_peptide Platypus
Ensembl Protein ID  
1090 inter\_paralog\_platypus\_chromosome Platypus Chromosome  
1091 inter\_paralog\_platypus\_chrom\_start Platypus Chromosome Start
(bp)  
1092 inter\_paralog\_platypus\_chrom\_end Platypus Chromosome End (bp)  
1093 inter\_paralog\_platypus\_orthology\_type Homology Type  
1094 platypus\_inter\_paralog\_subtype Ancestor  
1095 platypus\_inter\_paralog\_dn dS  
1096 platypus\_inter\_paralog\_ds dN  
1097 platypus\_inter\_paralog\_perc\_id % Identity  
1098 platypus\_inter\_paralog\_perc\_id\_r1 Platypus % Identity  
1099 inter\_paralog\_rabbit\_ensembl\_gene Rabbit Ensembl Gene ID  
1100 inter\_paralog\_rabbit\_inter\_paralog\_ensembl\_peptide Rabbit
Ensembl Protein ID  
1101 inter\_paralog\_rabbit\_chromosome Rabbit Chromosome  
1102 inter\_paralog\_rabbit\_chrom\_start Rabbit Chromosome Start (bp)  
1103 inter\_paralog\_rabbit\_chrom\_end Rabbit Chromosome End (bp)  
1104 inter\_paralog\_rabbit\_orthology\_type Homology Type  
1105 rabbit\_inter\_paralog\_subtype Ancestor  
1106 rabbit\_inter\_paralog\_dn dS  
1107 rabbit\_inter\_paralog\_ds dN  
1108 rabbit\_inter\_paralog\_perc\_id % Identity  
1109 rabbit\_inter\_paralog\_perc\_id\_r1 Rabbit % Identity  
1110 inter\_paralog\_rat\_ensembl\_gene Rat Ensembl Gene ID  
1111 inter\_paralog\_rat\_inter\_paralog\_ensembl\_peptide Rat Ensembl
Protein ID  
1112 inter\_paralog\_rat\_chromosome Rat Chromosome  
1113 inter\_paralog\_rat\_chrom\_start Rat Chromosome Start (bp)  
1114 inter\_paralog\_rat\_chrom\_end Rat Chromosome End (bp)  
1115 inter\_paralog\_rat\_orthology\_type Homology Type  
1116 rat\_inter\_paralog\_subtype Ancestor  
1117 rat\_inter\_paralog\_dn dS  
1118 rat\_inter\_paralog\_ds dN  
1119 rat\_inter\_paralog\_perc\_id % Identity  
1120 rat\_inter\_paralog\_perc\_id\_r1 Rat % Identity  
1121 inter\_paralog\_rhesus\_ensembl\_gene Rhesus Ensembl Gene ID  
1122 inter\_paralog\_rhesus\_inter\_paralog\_ensembl\_peptide Rhesus
Ensembl Protein ID  
1123 inter\_paralog\_rhesus\_chromosome Rhesus Chromosome  
1124 inter\_paralog\_rhesus\_chrom\_start Rhesus Chromosome Start (bp)  
1125 inter\_paralog\_rhesus\_chrom\_end Rhesus Chromosome End (bp)  
1126 inter\_paralog\_rhesus\_orthology\_type Homology Type  
1127 rhesus\_inter\_paralog\_subtype Ancestor  
1128 rhesus\_inter\_paralog\_dn dS  
1129 rhesus\_inter\_paralog\_ds dN  
1130 rhesus\_inter\_paralog\_perc\_id % Identity  
1131 rhesus\_inter\_paralog\_perc\_id\_r1 Rhesus % Identity  
1132 inter\_paralog\_pcapensis\_ensembl\_gene Rock Hyrax Ensembl Gene
ID  
1133 inter\_paralog\_pcapensis\_inter\_paralog\_ensembl\_peptide Rock
Hyrax Ensembl Protein ID  
1134 inter\_paralog\_pcapensis\_chromosome Rock Hyrax Chromosome  
1135 inter\_paralog\_pcapensis\_chrom\_start Rock Hyrax Chromosome Start
(bp)  
1136 inter\_paralog\_pcapensis\_chrom\_end Rock Hyrax Chromosome End
(bp)  
1137 inter\_paralog\_pcapensis\_orthology\_type Homology Type  
1138 pcapensis\_inter\_paralog\_subtype Ancestor  
1139 pcapensis\_inter\_paralog\_dn dS  
1140 pcapensis\_inter\_paralog\_ds dN  
1141 pcapensis\_inter\_paralog\_perc\_id % Identity  
1142 pcapensis\_inter\_paralog\_perc\_id\_r1 Rock Hyrax % Identity  
1143 inter\_paralog\_sloth\_ensembl\_gene Sloth Ensembl Gene ID  
1144 inter\_paralog\_sloth\_inter\_paralog\_ensembl\_peptide Sloth
Ensembl Protein ID  
1145 inter\_paralog\_sloth\_chromosome Sloth Chromosome  
1146 inter\_paralog\_sloth\_chrom\_start Sloth Chromosome Start (bp)  
1147 inter\_paralog\_sloth\_chrom\_end Sloth Chromosome End (bp)  
1148 inter\_paralog\_sloth\_orthology\_type Homology Type  
1149 sloth\_inter\_paralog\_subtype Ancestor  
1150 sloth\_inter\_paralog\_dn dS  
1151 sloth\_inter\_paralog\_ds dN  
1152 sloth\_inter\_paralog\_perc\_id % Identity  
1153 sloth\_inter\_paralog\_perc\_id\_r1 Sloth % Identity  
1154 inter\_paralog\_squirrel\_ensembl\_gene Squirrel Ensembl Gene ID  
1155 inter\_paralog\_squirrel\_inter\_paralog\_ensembl\_peptide Squirrel
Ensembl Protein ID  
1156 inter\_paralog\_squirrel\_chromosome Squirrel Chromosome  
1157 inter\_paralog\_squirrel\_chrom\_start Squirrel Chromosome Start
(bp)  
1158 inter\_paralog\_squirrel\_chrom\_end Squirrel Chromosome End (bp)  
1159 inter\_paralog\_squirrel\_orthology\_type Homology Type  
1160 squirrel\_inter\_paralog\_subtype Ancestor  
1161 squirrel\_inter\_paralog\_dn dS  
1162 squirrel\_inter\_paralog\_ds dN  
1163 squirrel\_inter\_paralog\_perc\_id % Identity  
1164 squirrel\_inter\_paralog\_perc\_id\_r1 Squirrel % Identity  
1165 inter\_paralog\_gaculeatus\_ensembl\_gene Stickleback Ensembl Gene
ID  
1166 inter\_paralog\_gaculeatus\_inter\_paralog\_ensembl\_peptide
Stickleback Ensembl Protein ID  
1167 inter\_paralog\_gaculeatus\_chromosome Stickleback Chromosome  
1168 inter\_paralog\_gaculeatus\_chrom\_start Stickleback Chromosome
Start (bp)  
1169 inter\_paralog\_gaculeatus\_chrom\_end Stickleback Chromosome End
(bp)  
1170 inter\_paralog\_gaculeatus\_orthology\_type Homology Type  
1171 gaculeatus\_inter\_paralog\_subtype Ancestor  
1172 gaculeatus\_inter\_paralog\_dn dS  
1173 gaculeatus\_inter\_paralog\_ds dN  
1174 gaculeatus\_inter\_paralog\_perc\_id % Identity  
1175 gaculeatus\_inter\_paralog\_perc\_id\_r1 Stickleback % Identity  
1176 inter\_paralog\_tarsier\_ensembl\_gene Tarsier Ensembl Gene ID  
1177 inter\_paralog\_tarsier\_inter\_paralog\_ensembl\_peptide Tarsier
Ensembl Protein ID  
1178 inter\_paralog\_tarsier\_chromosome Tarsier Chromosome  
1179 inter\_paralog\_tarsier\_chrom\_start Tarsier Chromosome Start
(bp)  
1180 inter\_paralog\_tarsier\_chrom\_end Tarsier Chromosome End (bp)  
1181 inter\_paralog\_tarsier\_orthology\_type Homology Type  
1182 tarsier\_inter\_paralog\_subtype Ancestor  
1183 tarsier\_inter\_paralog\_dn dS  
1184 tarsier\_inter\_paralog\_ds dN  
1185 tarsier\_inter\_paralog\_perc\_id % Identity  
1186 tarsier\_inter\_paralog\_perc\_id\_r1 Tarsier % Identity  
1187 inter\_paralog\_tenrec\_ensembl\_gene Tenrec Ensembl Gene ID  
1188 inter\_paralog\_tenrec\_inter\_paralog\_ensembl\_peptide Tenrec
Ensembl Protein ID  
1189 inter\_paralog\_tenrec\_chromosome Tenrec Chromosome  
1190 inter\_paralog\_tenrec\_chrom\_start Tenrec Chromosome Start (bp)  
1191 inter\_paralog\_tenrec\_chrom\_end Tenrec Chromosome End (bp)  
1192 inter\_paralog\_tenrec\_orthology\_type Homology Type  
1193 tenrec\_inter\_paralog\_subtype Ancestor  
1194 tenrec\_inter\_paralog\_dn dS  
1195 tenrec\_inter\_paralog\_ds dN  
1196 tenrec\_inter\_paralog\_perc\_id % Identity  
1197 tenrec\_inter\_paralog\_perc\_id\_r1 Tenrec % Identity  
1198 inter\_paralog\_tetraodon\_ensembl\_gene Tetraodon Ensembl Gene
ID  
1199 inter\_paralog\_tetraodon\_inter\_paralog\_ensembl\_peptide
Tetraodon Ensembl Protein ID  
1200 inter\_paralog\_tetraodon\_chromosome Tetraodon Chromosome  
1201 inter\_paralog\_tetraodon\_chrom\_start Tetraodon Chromosome Start
(bp)  
1202 inter\_paralog\_tetraodon\_chrom\_end Tetraodon Chromosome End
(bp)  
1203 inter\_paralog\_tetraodon\_orthology\_type Homology Type  
1204 tetraodon\_inter\_paralog\_subtype Ancestor  
1205 tetraodon\_inter\_paralog\_dn dS  
1206 tetraodon\_inter\_paralog\_ds dN  
1207 tetraodon\_inter\_paralog\_perc\_id % Identity  
1208 tetraodon\_inter\_paralog\_perc\_id\_r1 Tetraodon % Identity  
1209 inter\_paralog\_tree\_shrew\_ensembl\_gene Tree Shrew Ensembl Gene
ID  
1210 inter\_paralog\_tree\_shrew\_inter\_paralog\_ensembl\_peptide Tree
Shrew Ensembl Protein ID  
1211 inter\_paralog\_tree\_shrew\_chromosome Tree Shrew Chromosome  
1212 inter\_paralog\_tree\_shrew\_chrom\_start Tree Shrew Chromosome
Start (bp)  
1213 inter\_paralog\_tree\_shrew\_chrom\_end Tree Shrew Chromosome End
(bp)  
1214 inter\_paralog\_tree\_shrew\_orthology\_type Homology Type  
1215 tree\_shrew\_inter\_paralog\_subtype Ancestor  
1216 tree\_shrew\_inter\_paralog\_dn dS  
1217 tree\_shrew\_inter\_paralog\_ds dN  
1218 tree\_shrew\_inter\_paralog\_perc\_id % Identity  
1219 tree\_shrew\_inter\_paralog\_perc\_id\_r1 Tree Shrew % Identity  
1220 inter\_paralog\_wallaby\_ensembl\_gene Wallaby Ensembl Gene ID  
1221 inter\_paralog\_wallaby\_inter\_paralog\_ensembl\_peptide Wallaby
Ensembl Protein ID  
1222 inter\_paralog\_wallaby\_chromosome Wallaby Chromosome  
1223 inter\_paralog\_wallaby\_chrom\_start Wallaby Chromosome Start
(bp)  
1224 inter\_paralog\_wallaby\_chrom\_end Wallaby Chromosome End (bp)  
1225 inter\_paralog\_wallaby\_orthology\_type Homology Type  
1226 wallaby\_inter\_paralog\_subtype Ancestor  
1227 wallaby\_inter\_paralog\_dn dS  
1228 wallaby\_inter\_paralog\_ds dN  
1229 wallaby\_inter\_paralog\_perc\_id % Identity  
1230 wallaby\_inter\_paralog\_perc\_id\_r1 Wallaby % Identity  
1231 inter\_paralog\_yeast\_ensembl\_gene Yeast Ensembl Gene ID  
1232 inter\_paralog\_yeast\_inter\_paralog\_ensembl\_peptide Yeast
Ensembl Protein ID  
1233 inter\_paralog\_yeast\_chromosome Yeast Chromosome  
1234 inter\_paralog\_yeast\_chrom\_start Yeast Chromosome Start (bp)  
1235 inter\_paralog\_yeast\_chrom\_end Yeast Chromosome End (bp)  
1236 inter\_paralog\_yeast\_orthology\_type Homology Type  
1237 yeast\_inter\_paralog\_subtype Ancestor  
1238 yeast\_inter\_paralog\_dn dS  
1239 yeast\_inter\_paralog\_ds dN  
1240 yeast\_inter\_paralog\_perc\_id % Identity  
1241 yeast\_inter\_paralog\_perc\_id\_r1 Yeast % Identity  
1242 inter\_paralog\_zebra\_finch\_ensembl\_gene Zebra Finch Ensembl
Gene ID  
1243 inter\_paralog\_zebra\_finch\_inter\_paralog\_ensembl\_peptide
Zebra Finch Ensembl Protein ID  
1244 inter\_paralog\_zebra\_finch\_chromosome Zebra Finch Chromosome  
1245 inter\_paralog\_zebra\_finch\_chrom\_start Zebra Finch Chromosome
Start (bp)  
1246 inter\_paralog\_zebra\_finch\_chrom\_end Zebra Finch Chromosome End
(bp)  
1247 inter\_paralog\_zebra\_finch\_orthology\_type Homology Type  
1248 zebra\_finch\_inter\_paralog\_subtype Ancestor  
1249 zebra\_finch\_inter\_paralog\_dn dS  
1250 zebra\_finch\_inter\_paralog\_ds dN  
1251 zebra\_finch\_inter\_paralog\_perc\_id % Identity  
1252 zebra\_finch\_inter\_paralog\_perc\_id\_r1 Zebra Finch % Identity  
1253 inter\_paralog\_zebrafish\_ensembl\_gene Zebrafish Ensembl Gene
ID  
1254 inter\_paralog\_zebrafish\_inter\_paralog\_ensembl\_peptide
Zebrafish Ensembl Protein ID  
1255 inter\_paralog\_zebrafish\_chromosome Zebrafish Chromosome  
1256 inter\_paralog\_zebrafish\_chrom\_start Zebrafish Chromosome Start
(bp)  
1257 inter\_paralog\_zebrafish\_chrom\_end Zebrafish Chromosome End
(bp)  
1258 inter\_paralog\_zebrafish\_orthology\_type Homology Type  
1259 zebrafish\_inter\_paralog\_subtype Ancestor  
1260 zebrafish\_inter\_paralog\_dn dS  
1261 zebrafish\_inter\_paralog\_ds dN  
1262 zebrafish\_inter\_paralog\_perc\_id % Identity  
1263 zebrafish\_inter\_paralog\_perc\_id\_r1 Zebrafish % Identity  
1264 human\_paralog\_ensembl\_gene Human Paralog Ensembl Gene ID  
1265 human\_paralog\_chromosome Human Paralog Chromosome  
1266 human\_paralog\_chrom\_start Human Paralog Chr Start (bp)  
1267 human\_paralog\_chrom\_end Human Paralog Chr End (bp)  
1268 human\_paralog\_ensembl\_peptide Representative Protein ID  
1269 human\_paralog\_paralog\_ensembl\_peptide Human Paralog Ensembl
Protein ID  
1270 human\_paralog\_ancestor Ancestor  
1271 paralog\_hsap\_\_dm\_description\_4014 Homology Type  
1272 hsapiens\_dn dN  
1273 hsapiens\_ds dS  
1274 paralog\_hsap\_\_dm\_tag\_4060 Bootstrap/Duplication Confidence
Score Type  
1275 paralog\_hsap\_\_dm\_value\_4060 Bootstrap/Duplication Confidence
Score  
1276 paralog\_hsap\_\_dm\_perc\_id\_4015 % Identity  
1277 paralog\_hsap\_\_dm\_perc\_id\_4015\_r1 Human % Identity  
1278 ensembl\_gene\_id Ensembl Gene ID  
1279 ensembl\_transcript\_id Ensembl Transcript ID  
1280 ensembl\_peptide\_id Ensembl Protein ID  
1281 chromosome\_name Chromosome Name  
1282 start\_position Gene Start (bp)  
1283 end\_position Gene End (bp)  
1284 strand Strand  
1285 band Band  
1286 external\_gene\_id Associated Gene Name  
1287 external\_gene\_db Associated Gene DB  
1288 transcript\_count Transcript count  
1289 percentage\_gc\_content % GC content  
1290 description Description  
1291 source\_name SNP Source  
1292 source\_description Source description  
1293 external\_id Reference ID  
1294 allele Allele  
1295 validated Validation status  
1296 mapweight Mapweight  
1297 transcript\_location Transcript location (bp)  
1298 snp\_chromosome\_strand SNP Chromosome Strand  
1299 peptide\_location Protein location (aa)  
1300 chromosome\_location Chromosome Location (bp)  
1301 peptide\_shift Protein Allele  
1302 cds\_start\_2024 CDS Start  
1303 cds\_end\_2024 CDS End  
1304 transcript\_exon\_intron Unspliced (Transcript)  
1305 gene\_exon\_intron Unspliced (Gene)  
1306 transcript\_flank Flank (Transcript)  
1307 gene\_flank Flank (Gene)  
1308 coding\_transcript\_flank Flank-coding region (Transcript)  
1309 coding\_gene\_flank Flank-coding region (Gene)  
1310 5utr 5' UTR  
1311 3utr 3' UTR  
1312 gene\_exon Exon sequences  
1313 cdna cDNA sequences  
1314 coding Coding sequence  
1315 peptide Protein  
1316 upstream\_flank upstream\_flank  
1317 downstream\_flank downstream\_flank  
1318 ensembl\_gene\_id Ensembl Gene ID  
1319 description Description  
1320 external\_gene\_id Associated Gene Name  
1321 external\_gene\_db Associated Gene DB  
1322 chromosome\_name Chromosome Name  
1323 start\_position Gene Start (bp)  
1324 end\_position Gene End (bp)  
1325 family Ensembl Protein Family ID(s)  
1326 cds\_length CDS Length  
1327 cds\_start CDS Start  
1328 cds\_end CDS End  
1329 5\_utr\_start 5' UTR Start  
1330 5\_utr\_end 5' UTR End  
1331 3\_utr\_start 3' UTR Start  
1332 3\_utr\_end 3' UTR End  
1333 ensembl\_transcript\_id Ensembl Transcript ID  
1334 ensembl\_peptide\_id Ensembl Protein ID  
1335 strand Strand  
1336 transcript\_start Transcript Start (bp)  
1337 transcript\_end Transcript End (bp)  
1338 ensembl\_exon\_id Ensembl Exon ID  
1339 exon\_chrom\_start Exon Chr Start (bp)  
1340 exon\_chrom\_end Exon Chr End (bp)  
1341 strand Strand  
1342 rank Exon Rank in Transcript  
1343 is\_constitutive Constitutive Exon
