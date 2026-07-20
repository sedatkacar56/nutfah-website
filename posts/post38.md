🔗 SNN Graph and Jaccard Similarity — The Math Behind Seurat Clustering

When Seurat builds the Shared Nearest Neighbor (SNN) graph, it uses Jaccard similarity to weight connections between cells. Here's what that means:

📐 Jaccard Similarity = |A ∩ B| / |A ∪ B|

Where A and B are the sets of nearest neighbors for two cells.

Example:
- Cell 1's 20 neighbors: {c3, c7, c12, c15, c20, ...}
- Cell 2's 20 neighbors: {c7, c12, c15, c18, c22, ...}
- Shared neighbors (intersection): {c7, c12, c15} = 3
- All unique neighbors (union): 37
- Jaccard similarity = 3/37 ≈ 0.081

# Seurat uses Jaccard similarity automatically
seurat_obj <- FindNeighbors(seurat_obj, dims = 1:20)
# RNA_snn graph contains Jaccard-weighted edges

# Inspect the SNN graph
snn_mat <- seurat_obj@graphs$RNA_snn
# Values range from 0 (no shared neighbors) to 1 (identical neighborhoods)

🔑 Why Jaccard matters:
- Higher Jaccard score = cells are more similar
- Pruning low Jaccard edges removes noise (controlled by prune.SNN parameter)
- This is the foundation of Louvain/Leiden clustering

Default prune.SNN = 1/15: edges with Jaccard < 0.067 are removed.

#Seurat #SNN #Jaccard #Clustering #scRNAseq #Bioinformatics #GraphTheory #SingleCell
