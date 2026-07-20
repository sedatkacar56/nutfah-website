🧬 The default Wilcoxon test in FindAllMarkers() doesn't account for sequencing depth differences between cells. In mixed cell populations like PBMCs, this creates false positives — genes appearing upregulated simply due to higher sequencing coverage rather than true biology.

The solution: replace the default test with logistic regression and include nCount_RNA as a latent variable.

FindAllMarkers(
  seu,
  test.use = "LR",
  latent.vars = "nCount_RNA",
  min.pct = 0.25,
  logfc.threshold = 0.5
)

This ensures only true biological signal drives your marker calls — not technical variation in sequencing depth.

When to use which:
• Homogeneous datasets: Wilcoxon is acceptable
• Mixed / multi-lineage data: use logistic regression + latent variable correction

One line change. More honest biology.

#SingleCellRNAseq #Seurat #Bioinformatics #scRNAseq #ComputationalBiology #DifferentialExpression
