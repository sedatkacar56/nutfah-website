🔄 Converting Seurat to Scanpy / AnnData — A Practical Guide

Need to move your single-cell analysis from R to Python? Here's how to convert between Seurat and AnnData objects:

📦 Method 1: Using SeuratDisk (R → h5ad)

library(SeuratDisk)

# Save as h5Seurat first, then convert to h5ad
SaveH5Seurat(seurat_obj, filename = "my_data.h5Seurat")
Convert("my_data.h5Seurat", dest = "h5ad")

# In Python (Scanpy)
import scanpy as sc
adata = sc.read_h5ad("my_data.h5ad")

📦 Method 2: Using sceasy (more reliable)

library(sceasy)
library(reticulate)

sceasy::convertFormat(seurat_obj,
                      from = "seurat",
                      to = "anndata",
                      outFile = "my_data.h5ad")

🗂️ Understanding AnnData structure:
- adata.X → count matrix (cells × genes)
- adata.obs → cell metadata (like seurat@meta.data)
- adata.var → gene metadata
- adata.obsm → reductions (PCA, UMAP embeddings)
- adata.uns → unstructured data (like seurat@misc)

💡 Common issues:
- Assay names: Seurat uses "RNA", AnnData defaults to no assay name
- Sparse matrices: both use sparse; should transfer cleanly
- Reductions: may need to re-run UMAP in Scanpy for consistency

#Seurat #Scanpy #AnnData #scRNAseq #Python #RStats #Bioinformatics #SingleCell #DataConversion
