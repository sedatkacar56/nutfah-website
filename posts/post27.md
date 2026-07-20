🧬 AUCell vs. UCell for Gene Set Scoring in Single-Cell RNA-seq

Both AUCell and UCell score gene set activity per cell, but they differ in approach and integration.

🔹 AUCell (Bioconductor):
- Based on Area Under the Curve (AUC) of ranked gene expression
- Good for large gene sets
- Works well with SCENIC for regulon activity

library(AUCell)
rankings <- AUCell_buildRankings(exprMatrix)
geneSets <- list(MyGeneSet = c("Gene1", "Gene2", "Gene3"))
cells_AUC <- AUCell_calcAUC(geneSets, rankings)

🔹 UCell (part of escape R package):
- Uses Mann-Whitney U statistic (similar to AUC but more robust)
- Seamlessly integrates with Seurat
- Better for smaller gene sets and exploratory analysis

library(UCell)
seurat_obj <- AddModuleScore_UCell(
  seurat_obj,
  features = list(MySignature = c("Gene1", "Gene2", "Gene3"))
)

✅ When to use which:
- AUCell: SCENIC workflows, large regulons, Bioconductor pipelines
- UCell: Quick Seurat integration, flexible signatures, exploratory work

Both are rank-based and therefore robust to technical variation. Which do you prefer? 👇

#SingleCell #Bioinformatics #AUCell #UCell #GeneSetScoring #scRNAseq #RStats #escape
