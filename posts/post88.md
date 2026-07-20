[NOTE: This post was fetched as a summary only — original text may differ. Please verify against LinkedIn: https://www.linkedin.com/posts/sedat-kacar-phd-6863b812b_singlecell-scrnaseq-bioinformatics-activity-7369814285453070336-kQxP]

scDblFinder() parameters for better doublet detection:

clusters — cell-type labels so artificial doublets form between distinct biological groups
clustCor — adds correlation features to cluster profiles to detect mixed identity cells
samples — restricts detection within capture batches/wells

Combining all three gives cleaner calls, fewer false positives.

However, testing with various parameter combinations (default, with samples, with samples+annotations) showed no robust separation between doublets and singlets in UMAP. The algorithm efficiency in practice is worth questioning and validating.

#singlecell #scRNAseq #bioinformatics #Seurat #Bioconductor #DoubletDetection
