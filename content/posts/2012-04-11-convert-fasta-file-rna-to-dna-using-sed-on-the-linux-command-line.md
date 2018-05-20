+++
title = "Convert FASTA file RNA to DNA using sed on the linux command line"
slug = "2012-04-11-convert-fasta-file-rna-to-dna-using-sed-on-the-linux-command-line"
published = 2012-04-11T13:31:00-07:00
author = "Owen"
tags = []
+++
sed '/^[^>]/ y/uU/tT/' uracil.fasta > thymine.fasta 

Piece of cake.
