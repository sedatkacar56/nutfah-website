🧬 When analyzing large datasets with 100,000+ cells, FeaturePlot() automatically enables rasterization — converting cells to fixed pixels. This improves rendering performance but reduces visual clarity and can obscure important gene expression patterns.

Same data. Same gene. Different visualization setting. Different interpretation.

# Default for large datasets — rasterized, faster but lower resolution
FeaturePlot(seurat_obj, features = "CD4", raster = TRUE)

# Full resolution — slower but shows individual cell expression
FeaturePlot(seurat_obj, features = "CD4", raster = FALSE)

The risk: small but biologically significant expression clusters can become nearly invisible when rasterization compresses them to a few pixels. You might conclude a gene is absent in a population when it's actually expressed — just hidden by the default rendering setting.

🧠 Single-cell analysis requires understanding default settings. Parameters like raster = TRUE or FALSE significantly impact result interpretation. Knowing your tool's defaults is part of knowing your data.

#SingleCellRNAseq #Seurat #Bioinformatics #FeaturePlot #scRNAseq #DataVisualization #ComputationalBiology
