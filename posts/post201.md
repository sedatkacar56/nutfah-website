🧬 A quick tip that has saved many R sessions: when accessing large matrices from Seurat, never print them directly — and be careful with head() too.

The problem:

mat <- GetAssayData(seurat_obj, layer = "scale.data")
print(mat)       # 🔴 crashes R — too much output
head(mat, 10)    # ⚠️ limits rows, but still prints ALL columns

With 20,000+ cells, even head() can dump an enormous amount of output and freeze your session.

The solution:

head(mat, c(6, 2))   # ✅ 6 rows × 2 columns only

R matrices follow [rows, columns] syntax. Providing a vector to head() constrains both dimensions — small, controlled, readable.

🧠 Be intentional about what you print when working with single-cell data. Every matrix is potentially session-threatening. Treat them that way.
