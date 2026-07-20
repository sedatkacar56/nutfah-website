🧬 A common problem in single-cell RNA-seq research: you save an RDS file, come back months later, and have no idea which animal, condition, normalization, or parent dataset was used. The Seurat object is there — but the context is gone.

seuratPassport is an R package that solves this by embedding a "passport" directly into the Seurat object, stored in @misc$passport. The passport travels with the .rds file wherever it goes.

What the passport captures:
• Identity information — object name, creation date
• Animal/sample metadata — species, sex, age, condition, tissue
• Experiment details — project, researcher, processing notes
• Lineage tracking — parent objects and child subsets
• Processing logs with timestamps and cell counts

Key features:
• Interactive RStudio interface for data entry
• Automatic parent-child linking for subset objects
• Non-invasive storage — it doesn't modify your data, just adds metadata
• Simple installation via source() command

Reproducibility and research transparency matter. When you share an .rds file, the context should come with it.
