📐 What Are Eigenvalues in PCA? A scRNA-seq Explanation

When you run PCA on your single-cell data, you get eigenvalues. But what do they actually mean?

🔑 Eigenvalue = the amount of variance explained by each principal component

In scRNA-seq:
- PC1 has the largest eigenvalue → explains the most variation (often cell cycle, batch effects, or major cell type differences)
- PC2 explains the second most variation
- And so on...

# Access eigenvalues (standard deviations) in Seurat
pca_stdev <- seurat_obj@reductions$pca@stdev
eigenvalues <- pca_stdev^2  # Eigenvalue = variance = stdev²

# Plot elbow plot to decide how many PCs to use
ElbowPlot(seurat_obj, ndims = 50)

# Percent variance explained
pct_var <- eigenvalues / sum(eigenvalues) * 100
cumsum(pct_var)[1:20]  # Cumulative variance for first 20 PCs

💡 The elbow plot shows where eigenvalues stop dropping steeply — that's usually where you should cut off your PC selection.

Q: Why not just use all PCs?
A: Later PCs mostly capture noise, not biology. Using too many PCs makes clustering unstable and adds computational overhead.

Rule of thumb: 10-30 PCs for most scRNA-seq datasets, but always check your elbow plot!

#PCA #scRNAseq #Bioinformatics #Seurat #Eigenvalues #DimensionalityReduction #Statistics #SingleCell
