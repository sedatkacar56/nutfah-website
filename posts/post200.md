🧬 Cell Ranger outputs a genes × cells matrix. Rows are genes. Columns are cell barcodes. Seurat maintains this orientation internally.

But many statistical analysis tools expect cells × observations format — because cells are the observations (samples) and genes are the features (variables).

Inside Seurat, you never need to think about this. Seurat handles it internally. But when you extract matrices using GetAssayData(), you receive genes × cells format and must transpose using t(mat) for external tools.

Tools that require transposition:

mat <- GetAssayData(seurat_obj, layer = "scale.data")

# These tools expect cells × genes
prcomp(t(mat))        # PCA
dist(t(mat))          # Distance
cor(t(mat))           # Correlation
# Monocle3 trajectory analysis also expects cells as rows

This isn't data corruption — it's changing perspective. Biology-focused view: genes across cells. Statistics-focused view: cells defined by genes.

Understanding dimensional consistency prevents workflow errors when passing matrices between Seurat and external packages.
