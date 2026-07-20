🧬 "UMAP shows the story, but the neighbor graph carries the evidence."

UMAP is a compressed 2D representation designed for visualization. It does not preserve biological distances faithfully. Cells appearing proximate on a UMAP plot may differ substantially in actual gene expression space.

Common pitfalls:
• Visually "nearest" clusters may lack genuine biological similarity
• Scattered cells aren't inherently problematic — they could represent rare types or transitional states
• Forcing unlabeled cells into their nearest cluster risks misclassification

Before assigning cells to clusters based on UMAP proximity, examine QC metrics and validate with marker genes. Use graph-based clustering methods — FindNeighbors() and FindClusters() in Seurat — rather than relying solely on 2D coordinates.

UMAP provides intuitive visualization. Computational clustering in high-dimensional space provides the actual biological grounding.

The UMAP is for communication. The neighbor graph is for decisions.

#SingleCell #Seurat #Bioinformatics #UMAP #scRNAseq #ComputationalBiology #CellClustering
