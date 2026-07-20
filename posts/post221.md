🧬 Two essential tools in any bulk RNA-seq pipeline: STAR for alignment, featureCounts (from the Subread package) for quantification. They work sequentially.

STAR (Spliced Transcripts Alignment to a Reference):
• Fast alignment of RNA-seq reads to the reference genome
• Handles splice junctions — critical for RNA data
• Input: FASTQ files
• Output: BAM files (aligned reads)

featureCounts / Subread:
• Used after alignment
• Quantifies reads mapping to each annotated gene
• Input: BAM files + GTF annotation file
• Output: Gene count matrix (genes × samples)

The workflow:

FASTQ → (STAR) → BAM → (featureCounts) → count matrix → DE analysis

STAR handles the "where do these reads come from in the genome?" question. featureCounts handles "how many reads map to each gene?" question. The count matrix is the starting point for differential expression in DESeq2, edgeR, or limma.

🧠 Understanding the full pipeline — from raw reads to counts — helps you interpret what your QC metrics actually mean at each step.

#RNAseq #Bioinformatics #Genomics #STAR #featureCounts #Subread #ComputationalBiology #BulkRNAseq
