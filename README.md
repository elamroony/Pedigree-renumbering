# Pedigree-renumbering

Pedigree re-numbering:  
Sometimes we need to re-number the pedigree either because, for example, we would like to use it with a program that accepts only pedigree starts from 1 to n, where n is the number of animals, (for example to calculate numerator relationships) or because we would like to use numeric IDs instead of other IDs format (e.g., alphabetic IDs).

pedRenum renumbers the pedigree in two different ways:

Type 1 (T1): The pedigree gets renumbered starting from 1 and all parents that are not listed on the animal column (first column) get listed in file Sires_not_in_Animal_column.txt and file Dams_not_in_Animal_column.txt for sires and dams respectively.

Type 2 (T2): The pedigree gets renumbered starting from 1 and all parents that are not listed on  the animal column (first column) will be treated as missing (0). Such renumbered pedigree is useful, for example, in some genomic-based analyses where only genotyped animals (first column) need to be considered (dous and trios). Pedigree could be numeric, alphanumeric or a combination . 

Example:


Pedigree file:

H102	0	QQ3R
986	M3	A70
A70	RR77	W55W
W55W	986	0
969696	KK100K	TTTT5
NNN14	313	A70
M3	0	TTTT5
M4	M3	969696
S44S	313	969696
313	KK100K	D785D


renumPedT1.txt:

1    0   13    H102  
2    7    3    986   
3   11    4    A70   
4    2    0    W55W  
5   12   14    969696
6   10    3    NNN14 
7    0   14    M3    
8    7    5    M4    
9   10    5    S44S  
10   12   15    313  

renumPedT2.txt

1    0  0  H102  
2    7  3  986   
3    0  4  A70   
4    2  0  W55W  
5    0  0  969696
6   10  3  NNN14 
7    0  0  M3    
8    7  5  M4    
9   10  5  S44S  
10   0  0  313   

