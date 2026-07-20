Sometimes you think your markers are telling a complex biological story… and sometimes it's just a data-structure lesson 😄

After running FindAllMarkers() in Seurat, I noticed the same genes appearing across multiple clusters. At first, this feels wrong — aren't markers supposed to be unique? But that's not how FindAllMarkers() works. It tests each cluster vs all others, so shared programs (fibroblast, activation, EndoMT, spatial gradients) naturally show up again and again.

Then came a second "aha" moment — a more technical one. If you assign marker genes directly to rownames (as I did at first), R will silently enforce uniqueness by appending numbers:

Col3a1
Col3a11
Col3a12

Those are not new genes. They're just repeated instances of the same gene, automatically renamed to keep rownames unique. So what looks like biology can sometimes be bookkeeping.

Two reminders I'm taking with me:

📌 Repeated markers across clusters often mean shared biology, not errors
📌 Artificial gene suffixes (…1, …2) are a data-frame artifact, not biology

Clusters are labels. Programs are continuous. And rownames can quietly lie if we're not careful 🙂

Back to basics — again.

#SingleCell #SpatialTranscriptomics #Seurat #SCTransform #Bioinformatics #DataWrangling #LearningInPublic #AlMucib
