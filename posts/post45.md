🧬 Use (?i)mt- to Catch Mitochondrial Genes Across Species in R

When calculating percent mitochondrial content for QC in Seurat, species-specific gene naming can trip you up:

- Human: MT-CO1, MT-ND1 (uppercase)
- Mouse: mt-Co1, mt-Nd1 (lowercase mt-)
- Other species: varies!

The solution: use a case-insensitive regex pattern.

# The universal approach — works for human AND mouse
seurat_obj[["percent.mt"]] <- PercentageFeatureSet(
  seurat_obj,
  pattern = "(?i)^mt-"  # (?i) makes it case-insensitive
)

# Verify it caught the right genes
mt_genes <- rownames(seurat_obj)[grepl("(?i)^mt-", rownames(seurat_obj), perl = TRUE)]
head(mt_genes)

# Species-specific alternatives:
# Human: pattern = "^MT-"
# Mouse: pattern = "^mt-"
# Universal: pattern = "(?i)^mt-"

✅ The (?i) modifier at the start makes the entire pattern case-insensitive. The perl = TRUE argument is needed in base R grepl() for this to work, but Seurat's PercentageFeatureSet() handles it internally.

Never hardcode the pattern if your pipeline runs on multiple species!

#scRNAseq #Seurat #QualityControl #Mitochondrial #Regex #RStats #Bioinformatics #SingleCell
