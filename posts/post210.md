🧬 scPassport has been accepted into Bioconductor.

The package solves a practical problem: when sharing .rds files with collaborators, contextual metadata gets lost. The object travels — but the context doesn't.

scPassport embeds a "persistent metadata passport" directly inside the object rather than relying on external documentation.

Three main functions:
• scPassport(obj) — interactive Shiny interface for metadata entry
• read_passport(obj) — displays passport information
• log_step(obj) — records processing steps with timestamps

Works with Seurat objects, SingleCellExperiment, and SummarizedExperiment formats.

BiocManager::install("scPassport")

Thanks to Ruben A. for suggesting submission to CRAN, which inspired the broader Bioconductor submission.

#Bioconductor #Rstats #SingleCell #scRNAseq #OpenScience #Bioinformatics
