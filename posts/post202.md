🧬 Single-cell datasets are extremely sparse. A typical dataset with 10,000 cells and 30,000 genes creates 300 million data points — but 90–95% of them are zero. Most genes are not expressed in most cells.

Dense storage would consume gigabytes of memory and slow all computations to a crawl. Seurat instead uses sparse matrices — specifically dgCMatrix (Compressed Sparse Column format) — which only stores non-zero values and their positions, achieving dramatic memory efficiency.

The dual approach: not all steps stay sparse.

Raw counts and normalized data stay sparse — most values are still zero.
Scaled data becomes dense — centering and scaling operations fill in values across the entire matrix.

This conversion is necessary because algorithms like PCA, regression, and distance calculations require continuous values throughout the dataset. But it's also why ScaleData() uses the most memory of any step in the pipeline.

🧠 Mental model:
Sparse = store only signal
Dense = store signal + all empty space

Understanding this dual approach explains memory usage patterns, processing speeds, and why Seurat behaves differently across analytical layers. It's a data structure engineering decision as much as a biology one.
