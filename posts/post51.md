📊 Don't Miss Hidden NAs! Use table(useNA=) in Seurat Metadata QC

When exploring cell metadata in Seurat, a silent NA can corrupt your entire downstream analysis. The useNA parameter in table() makes them visible:

# Standard table() — hides NAs!
table(seurat_obj$cell_type)
# AT2    Club   Ciliated
#  1200   800     600

# With useNA = "ifany" — shows NAs only if present
table(seurat_obj$cell_type, useNA = "ifany")
# AT2    Club   Ciliated  <NA>
#  1200   800     600      45

# With useNA = "always" — always shows NA row
table(seurat_obj$cell_type, useNA = "always")

# For two-way tables (cross-tabulation)
table(seurat_obj$cell_type,
      seurat_obj$condition,
      useNA = "ifany")

✅ Three useNA options:
- "no" (default): ignores NAs silently
- "ifany": shows <NA> column only if NAs exist
- "always": always shows <NA> column

⚠️ Why this matters: If you have 45 unassigned cells (NA in cell_type) and use them in differential expression without knowing, your results will be confounded.

Always run table(useNA="ifany") on new metadata columns before analysis!

#RStats #Seurat #QualityControl #scRNAseq #Bioinformatics #Metadata #DataQuality
