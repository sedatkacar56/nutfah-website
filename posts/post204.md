🧬 A critical workflow principle for single-cell RNA-seq analysts: ggplot requires data frames, not Seurat objects.

What ggplot doesn't accept:
❌ Seurat objects (S4 containers with nested layers)
❌ Sparse matrices
❌ Raw biological data structures

What ggplot requires: a clean table where rows represent cells and columns represent variables — genes, clusters, metadata.

The solution is FetchData() before plotting:

df <- FetchData(seurat_obj, vars = c("UMAP_1", "UMAP_2", "seurat_clusters"))
ggplot(df, aes(UMAP_1, UMAP_2, color = seurat_clusters)) + geom_point()

The mindset shift: instead of "I have a Seurat object, let me plot it" — the approach should be "I need a clean data frame first."

FetchData() handles the extraction cleanly: it pulls UMAP coordinates, cluster identities, gene expression, and metadata into one flat table that ggplot can actually work with. This eliminates a common source of plotting errors that stem from incorrect data structure preparation.
