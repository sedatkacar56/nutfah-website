🔍 inherits() vs. is() in R — Why It Matters in Seurat & Bioinformatics

A Seurat object has multiple classes: "Seurat" and "list". Using class(pbmc) == "Seurat" can return FALSE or a vector, making it unreliable.

Use inherits(x, "Seurat") instead — it safely checks if an object is of a specific class or inherits from it, working with S3, S4, and RC objects.

Examples:
Seurat objects: inherits(x, "Seurat")
Data frames: inherits(x, "data.frame")
Matrices: inherits(x, "matrix")
ggplot objects: inherits(x, "gg")
Bioconductor S4: inherits(x, "ExpressionSet")

The is() function is S4-specific and unreliable for S3 objects like Seurat. Use it only for "SummarizedExperiment" and similar S4 classes.

Use inherits() for general checking, is() for S4 objects, and avoid class(x) == "name" patterns.

#rstats #bioinformatics #Seurat #SingleCell #RProgramming
