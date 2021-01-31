---
id: f1d642a2-d404-464e-8f48-c3641a5a5202
title: Forward Stool Methods
desc: ''
updated: 1611935365244
created: 1611935365244
---
**Extraction and Library Preparation**
One to one hundred fifty milligrams of stool (depending on the quantity on any given swab) was vortexed for 60 seconds in residual storage medium (Becton Dickenson Sterile Pack) and centrifuged at full speed in a microfuge for 5 min. Supernatant was gentle removed and put to waste, leaving a residual pellet.  The pellet was resuspended in 140 microliters of 10 mM Tris-EDTA, pH 8 with the addition of 1.4 microliters of 25 mg /ml lysozyme (Sigma-Aldrich) and incubated for 30 min at 37 C. Twenty three microliters of 1 mg/ml proteinase K (Sigma) and 0.14 microliters of 20% SDS was added per sample followed by incubation for 1 hr at 55 C with light vortexing each 15 min.  The samples were subsequently shaken at 140 RPM for 5 min.  

To each sample , 240 ul of extraction buffer (GITC; Oberacker, P., Stepper, P., Bond, D. M., Höhn, S., Focken, J., Meyer, V., Schelle, L., Sugrue, V. J., Jeunen, G.-J., Moser, T., Hore, S. R., von Meyenn, F., Hipp, K., Hore, T. A., & Jurkowski, T. P. (2019). Bio-On-Magnetic-Beads (BOMB): Open platform for high-throughput nucleic acid extraction and manipulation. _PLoS Biology_, _17_(1), e3000107.) was added and shaken at 1400 RPM for 5 min followed by centrifugation for 3 min at maximum speed in a microcentrifuge (13,500 RPM)  The supernatant was transferred to a new tube and 320 microliters of isopropanol was added. The mixture was chaken at 1400 RPM for 5 min at room temperature. 

Silica coated magnetic beads (BioXX) prepared nucleic acid free by DEPC treatment were added (20 microliters of bead density in original packaging) to each extraction and shaken for 5 min at RT, 1400  RPM. The beads were collected on a magnetic stand and the liquid phase sent to waste. The beads were washed with 400 microliters of pure isopropanol followed by two treatments of 300 microliters of 80% ethanol, each with 2 min of shaking at 1400 RPM to mix the wash and the beads.  After collecting the beads from the final wash, the wash was removed and the beads dried for 10 min at 50 C.  The purified DNA was eluted in 70 microliters of 5 mM Tris-HCl, pH 8.5, with shaking for 5 min. 

Shotgun DNA Illumina-compatible sequencing libraries were prepared using the iGenomix Riptide kit with the following parameters. Each preparation was initiated with approximately 50 ng of DNA (Quant-it dsDNA High Sensitivity Assay) circumstances, the initial stool swabs had low content and as much DNA as could be concentrated was used in the reactions. One microliter of the Low GC and High GC primers were used in Reaction A.  SPRI beads were used as per the protocol for primer separation and size selection.  The recommended treatment of Reaction A with 0.1 N sodium hydroxide was performed to avoid primer dimers and primer carry through. All reactions were sequenced on an Illumina Novaseq using a 150 bp PE protocol.

**Microbiome Sequence Analysis**
Raw sequences as fastq files were demultiplexed using fgbio demux as per the Riptide Kit recommendations. Sequences were trimmed and quality filtered using AfterQC (REF). Human sequences were removed by filtering using Kneaddata (REF).  Sequences were classified using the tool Kaiju (REF) and the NCBI nr database (REF).  Subsequent analyses were performed in the R environment using packages tidyverse, phyloseq, ..........................

**Measurement of fecal microbiota biomass**
As a surrogate measure the fecal biomass was determined using a quantitive Taqman PCR as described by Price et al (REF).  This assay targets universal portions of the 16rRNA gene. A standard curve was performed using the _E. coli_  16S rRNA gene cloned on a plasmid. The gene copies were normalized by the amount of input extracted stool.  

