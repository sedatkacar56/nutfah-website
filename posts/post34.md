🗺️ Reactome vs. GO vs. KEGG — Which Pathway Database Should You Use for scRNA-seq?

All three are popular for pathway enrichment analysis, but they have different strengths:

🔵 Gene Ontology (GO):
- Three hierarchies: Biological Process (BP), Molecular Function (MF), Cellular Component (CC)
- Largest coverage, most genes annotated
- Best for broad functional characterization
- ✅ Use when: you want comprehensive, standardized annotations

🟠 KEGG (Kyoto Encyclopedia of Genes and Genomes):
- Metabolic pathways and disease maps
- Manual curation with detailed pathway diagrams
- Best for metabolic and signaling pathways
- ✅ Use when: you want metabolic pathway context

🟣 Reactome:
- Human-focused, manually curated
- Hierarchical pathway structure
- Best for detailed molecular mechanisms
- ✅ Use when: you want mechanistic detail, especially for human disease

library(clusterProfiler)
library(org.Hs.eg.db)

# GO enrichment
ego <- enrichGO(gene = deg_genes,
                OrgDb = org.Hs.eg.db,
                keyType = "SYMBOL",
                ont = "BP",
                pAdjustMethod = "BH")

# KEGG enrichment
ekegg <- enrichKEGG(gene = entrez_ids,
                    organism = "hsa",
                    pAdjustMethod = "BH")

# Reactome
library(ReactomePA)
ereact <- enrichPathway(gene = entrez_ids,
                        organism = "human")

💡 My approach: Use GO for discovery, KEGG for metabolic context, Reactome for mechanism. Run all three and compare!

#PathwayAnalysis #GO #KEGG #Reactome #Bioinformatics #scRNAseq #GeneOntology #clusterProfiler
