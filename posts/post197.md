💡 Did you know Seurat can estimate the cell-cycle phase of every single cell? Using the built-in function CellCycleScoring() from Seurat, it scores cells based on known cell-cycle genes and assigns each cell to a phase.

🔬 Three phases are predicted:
🟢 G1 — cell growth
🟡 S phase — DNA replication
🔴 G2/M — preparation for mitosis

Seurat calculates two scores: S.Score and G2M.Score, then assigns a predicted Phase to every cell in the metadata.

⚙️ Example:

pbmc <- CellCycleScoring(
  object = pbmc,
  s.features = cc.genes$s.genes,
  g2m.features = cc.genes$g2m.genes)

Now every cell carries its predicted cell-cycle phase.

⚠️ Important detail many researchers miss: The default Seurat cell-cycle gene lists were originally curated from human genes. So if your dataset is mouse, rat, or another organism, you usually need to adapt gene names.

Example:
Human: MKI67
Mouse: Mki67

Small difference. But ignoring it can affect your scoring.

📊 Why this matters: Cell cycle is one of the strongest sources of variation in single-cell data. It can create artificial clusters, mask biological signals, or reveal proliferating populations. Many pipelines therefore visualize cell-cycle phases, regress out cell-cycle effects, or specifically study cycling cells.

🧠 Single-cell RNA-seq reveals more than cell types. It reveals cell states. And the cell cycle is one of the most important hidden states inside your data.

#SingleCellRNAseq #Seurat #Bioinformatics #ComputationalBiology #Genomics #Transcriptomics #RStats #DataScience #CellCycle #OpenScience #scRNAseq #SingleCellAnalysis #SystemsBiology #Bioconductor #ClusterAnalysis #UMAP #DataVisualization
