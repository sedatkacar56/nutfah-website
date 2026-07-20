✂️ Clean orig.ident Labels with substr() in Seurat

When loading multiple 10x samples, the orig.ident often gets messy sample names like "patient_001_GEX_filtered_matrix" instead of just "patient_001".

substr() is perfect for extracting just the part you need:

# Example: orig.ident = "SAMPLE_001_GEX"
# Want just: "SAMPLE_001"

# substr(x, start, stop)
seurat_obj$sample_id <- substr(seurat_obj$orig.ident, 1, 10)

# Or use gsub() for pattern-based cleaning
seurat_obj$sample_id <- gsub("_GEX.*$", "", seurat_obj$orig.ident)

# Using sub() to remove a prefix
seurat_obj$sample_id <- sub("^PATIENT_", "", seurat_obj$orig.ident)

# Practical example: extract first 8 characters
seurat_obj$patient_id <- substr(seurat_obj$orig.ident, 1, 8)

# Verify the result
table(seurat_obj$patient_id)

💡 When to use each:
- substr(): when you know the exact position
- gsub(): when you have a pattern to remove (regex)
- sub(): when you only want to remove the first match

Clean metadata labels make downstream analysis and visualization much easier!

#RStats #Seurat #DataCleaning #scRNAseq #RProgramming #Bioinformatics #Metadata
