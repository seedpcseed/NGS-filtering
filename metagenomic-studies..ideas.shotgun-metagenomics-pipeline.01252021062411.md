---
id: 7a7b68c5-bf08-40a8-a7e9-5d34bb0f821e
title: Shotgun Metagenomics Pipeline Ideas 01252021062411
desc: ''
updated: 1611935365246
created: 1611935365246
---
\#metagenomics 

# January 25, 2021

rawseqs
\->
fastp
\->
bbduk against contaminants
\->
FLASH
\->
mmseqs2 tax against uniref/swiss
\->
plass assembly
\->
prokka 

