🏘️ Understanding FindNeighbors() in Seurat — A Neighborhood Metaphor

Imagine each cell in your dataset is a house in a city. FindNeighbors() figures out which cells live "next door" to each other based on their gene expression profiles.

Here's what it does:
1️⃣ Takes your PCA embeddings (the "address" of each cell in reduced space)
2️⃣ Finds the k nearest neighbors for each cell (default k=20)
3️⃣ Builds two graphs: KNN graph + SNN graph (Shared Nearest Neighbor)

# Basic usage
seurat_obj <- FindNeighbors(seurat_obj,
                              dims = 1:20,    # which PCs to use
                              k.param = 20)   # number of neighbors

# The result: two graphs stored in the object
# seurat_obj@graphs$RNA_nn   # KNN graph
# seurat_obj@graphs$RNA_snn  # SNN graph

🔑 Why it matters:
- More neighbors (higher k) → smoother clusters, better for large datasets
- Fewer neighbors (lower k) → finer resolution, better for rare populations
- This step MUST come before FindClusters()

The SNN graph is what clustering algorithms actually use — cells sharing many neighbors are likely the same cell type.

#Seurat #scRNAseq #FindNeighbors #SingleCell #Clustering #Bioinformatics #KNN #SNN
