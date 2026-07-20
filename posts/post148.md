🔬 A reminder from single-cell analysis: UMAP is a tool, not the truth

I started with all cells and performed a standard unsupervised clustering (Panel A). From there, I subset the cells of interest, re-normalized, re-ran dimensionality reduction, and re-clustered them (Panel C).

Now here's the key observation 👇

After reclustering, Cluster 7 forms a very clean, isolated "island" of cells (Panel C). At first glance, this looks like a well-defined biological population after subseting the cells.

However…

When I map the exact same cells back to the original UMAP containing all cells (Panel A), those Cluster 7 cells are not cohesive at all — they are scattered across multiple regions, with no obvious structure.

In Panel B, you can see which original unsupervised Seurat clusters these cells came from. They originate from multiple clusters, not a single coherent group.

📌 Take-home message:
Clustering after subsetting can create apparent structure that did not exist in the global context. This doesn't mean reclustering is wrong — it can be extremely powerful — but it must be interpreted carefully and always cross-checked against:
the original embedding
cluster connectivity
marker consistency
and biological plausibility

🔍 Know your cells. Know your data. Don't blindly follow UMAP islands — pay attention to how clusters relate to each other across analyses.

scRNA-seq is as much reasoning as it is computation.

#SingleCellRNAseq #scRNAseq #Bioinformatics #Seurat #UMAP #DataInterpretation #Clustering #ComputationalBiology #Transcriptomics #KnowYourData #DataScience #SystemsBiology #Alhamdulillah
