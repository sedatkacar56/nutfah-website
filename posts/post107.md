I'm working on a Linux-based HPC cluster via SSH. I have 16 single cell batch files and want to submit all at the same time as a slum job, I did this: $for i in {1-16}; > sbatch Rtrun${i}.sh; >done Is this correct? If not, how many and what changes do we need to make it work? And Why did you do this particular change?

#BashScripting #IterationLoop #SinglecellRNAseq #Automation #HPCComputing #LinuxCommands #AcademicResearch
