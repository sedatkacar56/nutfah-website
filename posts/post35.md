⚠️ Should You Use GAPDH for Normalization in scRNA-seq? No — Here's Why

A common question I see from wet lab researchers transitioning to bioinformatics: "Can I normalize scRNA-seq data using GAPDH like in qPCR?"

Short answer: No — and here's why:

🔴 Why GAPDH fails in scRNA-seq:
- scRNA-seq captures only ~5-10% of transcripts per cell (high dropout rate)
- GAPDH may not be captured in every cell
- GAPDH expression varies between cell types and conditions
- Single reference genes are unreliable at single-cell resolution

✅ What we use instead:

1️⃣ Library size normalization (total count normalization):
Divide each cell's counts by total counts, multiply by scaling factor (usually 10,000)

# In Seurat
seurat_obj <- NormalizeData(seurat_obj,
                             normalization.method = "LogNormalize",
                             scale.factor = 10000)

2️⃣ SCTransform (regularized negative binomial regression):
Corrects for sequencing depth variation more robustly

seurat_obj <- SCTransform(seurat_obj, vars.to.regress = "percent.mt")

3️⃣ Scran pooling normalization:
Handles zero-inflated data better for rare cell types

The key insight: in scRNA-seq, we normalize by total transcriptome captured, not by a single reference gene.

#scRNAseq #Normalization #GAPDH #Bioinformatics #SingleCell #Seurat #SCTransform #Scran
