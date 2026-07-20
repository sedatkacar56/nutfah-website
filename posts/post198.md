🧬 Your Seurat object doesn't store one matrix. It stores three. Same biology. Three representations. Each optimized for a different purpose.

🔹 Raw Counts
Original UMI counts from sequencing, unnormalized. Your ground truth. Best for differential expression, pseudobulk analyses, and methods that assume count distributions.

🔹 Normalized Data (data layer)
Log-normalized and adjusted for sequencing depth. Your biological signal — cleaned. Optimal for visualization (FeaturePlot, VlnPlot), marker exploration, and interpretation.

🔹 Scaled Data (scale.data)
Centered and variance-scaled, often with regression applied. Your machine-learning-ready matrix. Ideal for PCA, clustering, and dimensionality reduction.

Use GetAssayData() with explicit layer specification:

GetAssayData(object, layer = "counts")
GetAssayData(object, layer = "data")
GetAssayData(object, layer = "scale.data")

Common mistakes: running differential expression on scaled data, or forgetting which normalization was applied. The wrong layer gives you the wrong answer — even if the code runs without errors.

🧠 Your result is only as valid as the layer you used.
