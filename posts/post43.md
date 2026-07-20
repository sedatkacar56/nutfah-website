📄 R Markdown Chunk Options — The Ones I Use Most in scRNA-seq Reports

After years of writing R Markdown reports for single-cell analysis, these chunk options save me the most time:

# Global defaults at the top of your .Rmd
knitr::opts_chunk$set(
  echo = TRUE,       # Show code
  eval = TRUE,       # Run code
  message = FALSE,   # Hide messages (great for package loading)
  warning = FALSE,   # Hide warnings
  cache = TRUE,      # Cache slow chunks (huge time saver!)
  fig.width = 10,    # Figure width in inches
  fig.height = 8,    # Figure height
  dpi = 150          # Resolution
)

# Per-chunk: override for specific chunks
# ```{r umap-plot, cache=FALSE, fig.width=12}
# DimPlot(seurat_obj)
# ```

# Useful individual options:
# include = FALSE   → run code but hide everything
# results = 'hide'  → hide text output but show plots
# out.width = "100%" → full width figures
# fig.cap = "UMAP"  → figure caption

💡 My top 3 tips:
1. Set cache=TRUE globally — RunPCA and RunUMAP take forever. Cache them.
2. Set message=FALSE and warning=FALSE globally — package messages are noisy
3. Use fig.width/fig.height per chunk for complex multi-panel plots

Do you use R Markdown for your bioinformatics reports? 📊

#RMarkdown #RStats #knitr #Bioinformatics #scRNAseq #ReproducibleResearch #DataScience
