---
id: 423d8393-a714-465e-a783-94cee8adf2e7
title: Workflow for Metagenomics in R
desc: ''
updated: 1611935365248
created: 1611935365248
---
\#workflow #metagenomics #R #drake

# Workflow for Metagenomics in R

### Key considerations for 'why'

1. Want to make something reproducible
2. Ideally has markup to allow for notes about decisions and analytic choices or issues
3. Should use a DAG or other method to track steps  completed and not (reduce reruns that aren't needed)
4. Should use containers to allow for maximum portability
5. Should be **VERY** **flexible**
6. Due to (5), should allow for assembled, assembly-free, and amplicon metagenomics as well as analysis and visualization steps.
7. I'm targeting the writing in R because it uses the power of the language for all steps and reduces the amount I have to swtich coding (which slows me down)

### Needs a configuration file (**config.R**)

1. Should hold the values assigned to paths and containers needed. 
2. Can also designate run variables like memory and threads as needed
3. Can simply be an R file that is sourced in R (making it easy; variables are loaded right up )

### Needs a file with 'rules' (**rules.R**)

1. This defines the code for each type of module that may be used
2. Determines what flags go into the calls made (since most will be to containers)

### Needs a RFlow file (**RFlow.R**)

### Needs a helpers code file (**helpers.R**)

1. Script to send rules, variables, and flags to calls
2. Download databases as needed
3. Install packages needed

### Flag System

1. If !exist make a directory in main path for .metaflow (so hidden)
2. In the .metaflow directory will be an RDS file containing flags in a data.frame
   1. In each module go through all the steps and calls
      1. Write the step #, call, date-time stamp, and complete binary
      2. Run through the steps and calls
      3. make a step complete=TRUE when done
   2. At the beginning of a module, load the RDS file (and thus data.frame)
      1. compare the loaded data.frame to a calculated frame at the start of the module 
      2. If steps are added to the new frame then they are done specifically.

