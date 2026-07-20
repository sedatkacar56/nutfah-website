🔬 Seurat's #FindClusters() is great, but have you explored #FindSubCluster()?

Anyone familiar with #singlecellRNAseq analysis in #Seurat knows that FindClusters() is essential for identifying broad cell populations. But what if we suspect that a specific cluster might need further #subclustering, and we don't want to increase the clustering resolution for the entire dataset? 🤔

💡 That's where FindSubCluster() comes in!

In Graph 1, Cluster 0 looks like it might contain additional subpopulations. Instead of increasing the resolution globally, I applied FindSubCluster() only to Cluster 0. The result? Graph 2, where Cluster 0 is now subdivided into meaningful subclusters (e.g., 0_0, 0_1, 0_2, etc.)—all while keeping the rest of the dataset intact. 🎯

🚀 Why use FindSubCluster()?
✔ More granularity without over-clustering other cell types.
✔ Targets specific clusters for deeper exploration (e.g., immune cell subtypes).
✔ Maintains biological context, avoiding unnecessary fragmentation.
✔ Most importantly, annotators know this struggle—this helps annotate small subclusters within a larger cluster. If a specific subset expresses key markers (e.g., a T-cell subpopulation), FindSubCluster() makes it easier to identify without manually searching for barcodes.

---

🧬 Code to subcluster a specific cluster
seurat_object<- FindSubCluster(seurat_object, cluster = "", graph.name = "graph_type", resolution = )
DimPlot(seurat_object, group.by = "sub.cluster")

---

This approach is especially useful when broad clustering might not capture all biologically relevant subtypes.

#SingleCellRNAseq #Seurat #Bioinformatics #DataScience #UMAP #Clustering #FindSubCluster #FindClusters #Rprogramming #R #unsupervisedclustering #ArRabb
