🧬 R's short-circuit OR operator (||) evaluates conditions left-to-right and stops at the first TRUE value. This protects your data pipelines in three critical ways:

1. Prevents conditions that would throw errors if reached
2. Skips unnecessary expensive computations
3. Avoids operations on non-existent objects

Example 1 — Seurat validation:

# Safe: checks for NULL before calling ncol()
if (is.null(seurat_obj) || ncol(seurat_obj) < 100) {
  stop("Object is empty or too small")
}

If seurat_obj is NULL, R stops after the first condition. It never tries to call ncol() on a NULL object — which would crash.

Example 2 — File safety:

if (!file.exists(path) || file.size(path) == 0) {
  stop("File missing or empty")
}

Testing file existence before checking file size avoids unnecessary disk reads and downstream errors.

Core principle: place the cheapest or most critical condition first. || automatically skips remaining conditions when the first one is TRUE.

🧠 Particularly valuable in single-cell pipelines where data integrity checks are essential for reliable analysis.

#Rstats #Bioinformatics #SingleCellRNAseq #Seurat #ComputationalBiology #DataScience
