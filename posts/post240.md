🚀 You'll thank me when you learn about "dry run" mode.

I used to submit a SLURM job, wait in the queue ⏳, finally get resources allocated... only to discover that my pipeline failed in the first few seconds.

Why?

* Wrong file path ❌
* Missing reference directory ❌
* Typo in a filename ❌
* Missing input file ❌
* Incorrect configuration ❌

Then I had to:

1. Fix the mistake.
2. Submit another job.
3. Wait for resources again.
4. Hope I didn't miss another typo.

It was a frustrating cycle.

Then I discovered dry run mode.

A dry run validates your command and configuration without actually running the analysis. It checks whether the required files, directories, and parameters are available before consuming hours of compute time.

Think of it as pressing "Preview" before printing a 500-page document.

For example, many bioinformatics tools and workflow managers support a dry run option, including:

✅ Cell Ranger (`--dry`)
✅ Nextflow (`-preview` or validation features, depending on the workflow)
✅ Snakemake (`-n` / `--dry-run`)
✅ Many HPC pipelines and workflow frameworks

Instead of learning about an error after waiting in the queue, you find out in seconds.

This small habit has saved me countless hours of waiting, resubmitting jobs, and debugging.

💡 Before launching your next long-running analysis, ask yourself:

"Can I do a dry run first?"

Your future self—and your HPC cluster—will thank you.

#Bioinformatics #SingleCell #CellRanger #HPC #Linux #SLURM #Nextflow #Snakemake #ComputationalBiology #Genomics #ResearchComputing #AlBari #TheOriginator
