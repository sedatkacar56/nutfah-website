🧬 A common source of confusion when working with Seurat objects: different slots use different matrix orientations. You switch between examining the expression matrix and accessing metadata, and your brain goes: "Wait — did Seurat transpose my data?"

It didn't. Here's what's actually happening:

Data organization in Seurat:
• Expression matrices maintain genes × cells format
• Metadata slots use cells × features format
• Dimensional reductions (PCA, UMAP) follow cells × components structure

Different components serve distinct purposes. Expression data prioritizes gene-first organization (you think about which genes are expressed). Annotations and embeddings prioritize cell-first organization (you think about which cells have which properties).

🔍 Practical debugging: use dim() to verify dimensions before making assumptions about data orientation.

Understanding this eliminates the perception that Seurat is moving or transposing your data. The matrix isn't flipped — you're just looking at it from a different angle.
