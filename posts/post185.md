🧬 Understanding Single-Cell RNA-seq Raw Data
Barcodes · Features · Matrix Files

When you download a single-cell RNA-seq dataset from GEO, you'll usually see three files:

📁 *_barcodes.tsv.gz
📁 *_features.tsv.gz
📁 *_matrix.mtx.gz

Together, these three files define your entire experiment 👇

🧬 Which genes were measured → features.tsv.gz
🧫 Which cells were captured → barcodes.tsv.gz
🔢 How many UMIs were detected per gene per cell → matrix.mtx.gz

Think of it like this:
Features = rows (genes)
Barcodes = columns (cells)
Matrix = counts (expression values)

No magic. Just structured sparse data.

📄 Why are genes and barcodes stored as .tsv?

Because:
.tsv = Tab-Separated Values
.csv = Comma-Separated Values

Tabs are preferred in bioinformatics because:
Gene names sometimes contain commas
It avoids parsing confusion
It's cleaner for structured biological data

And genes/barcodes are simple one-column lists — .tsv is perfect for that.

🧮 Why .mtx for the matrix?

Because single-cell data is sparse. Most gene–cell combinations are zero. If stored as .tsv, you'd save millions of unnecessary zeros.

.mtx stores only non-zero values, making it:
Space-efficient
Faster to read
Designed for large sparse matrices

📦 Structure of .mtx (Matrix Market format)

1️⃣ Header
2️⃣ Matrix dimensions
3️⃣ Rows of: row column value
(Only non-zero counts are recorded.)

📦 Why are all files .gz?

Because they're compressed with gzip to drastically reduce file size and speed up downloads — especially important for large genomics datasets.

Three simple files. One entire transcriptomic landscape. 🌍

#SingleCell #scRNAseq #Bioinformatics #GEO #DataScience #ComputationalBiology #ArRaheem #TheBestoweroftheMercy
