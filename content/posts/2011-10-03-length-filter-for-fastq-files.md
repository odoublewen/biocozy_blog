+++
title = "Length filter for fastq files"
slug = "2011-10-03-length-filter-for-fastq-files"
published = 2011-10-03T09:41:00-07:00
author = "Owen"
tags = []
+++
I wanted to remove all sequences less than n long from a fastq file. 
This is a solution that uses sed "paragraphs" -- see my earlier post. 
It works... could probably be done more efficiently... but this works
for me, for now.  
  
Save this as a script, and then use in this manner:  
  
./fastqlenfilt.sh 15 input.fastq &gt;output.filtered.fastq  

    #!/bin/sh
    sed -n '                                                                                                                                                     
     # thanks to http://www.grymoire.com/Unix/Sed.html                                                                                                           
     #                                                                                                                                                           
     # if matching description, check the paragraph                                                                                                              
     /^@/ b para                                                                                                                                                 
     # else add it to the hold buffer                                                                                                                            
     H                                                                                                                                                           
     # at end of file, check paragraph                                                                                                                           
     $ b para                                                                                                                                                    
     # now branch to end of script                                                                                                                               
     b                                                                                                                                                           
     # this is where a paragraph is checked for the pattern                                                                                                      
     :para                                                                                                                                                       
     # return the entire paragraph                                                                                                                               
     # into the pattern space                                                                                                                                    
     x                                                                                                                                                           
     # look for the pattern, if there - print                                                                                                                    
     # /'.*\n.{$1,}'/ p                                                                                                                                          
      /'.*\\n[ACGTURYKMSWBDHVNX]\\{$1,\\}'/ p                                                                                                                    
     ' $2
