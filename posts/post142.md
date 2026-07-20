🔍 DotPlot in Seurat — split.by vs group.by: what no one warns you about

Visualizing expression across conditions using DotPlot()? You might be tempted to use split.by. But here's why grouping first is the safer move. 🧵

1/ 🧠 The problem with split.by: It splits cells within a group (e.g., cell type) by condition (e.g., hypoxia vs control) — but it doesn't recompute expression scales per split. So if one condition has fewer cells or different scale dynamics, you get distorted visuals.

2/ 📉 This leads to misleading interpretation — especially when comparing:
-Uneven sample sizes
-Subtle differences
-Broadly variable genes
The dots and colors can look off, not because of biology — but because of how the function works.

3/ ✅ What to do instead: Predefine your groups clearly:
seurat$group_label <- paste(seurat$condition, seurat$celltype, sep = "_")
Then use:
DotPlot(seurat, group.by = "group_label", features = ...)

4/ 🔒 Why this is better:
Consistent scaling per group
Transparent comparisons
Safer across conditions and cell types
Clean input → honest output
It puts you in control, not the function.

5/ 💬 Have you run into scaling issues using split.by? How do you compare conditions within cell types?

#Seurat #scRNAseq #SingleCell #Bioinformatics #DataVisualization #DotPlot #RStats #ComputationalBiology #AlAlim
