Hey, it is good to know some particular flares of databases. Some letters, symbols... That is why I share this post to give you some insights, which will make your search easier. Here you go... 🚀 

How to Quickly Recognize GEO & SRA Accessions

When you dig into public single-cell datasets, you see a jungle of IDs like GSE131776, GSM3819837, SRX5904090, SRR9130203… 🌀 

Here's a quick guide I use to recognize them at a glance:

🔹 GSE = GEO Series (the whole study / project page)
🔹 GSM = GEO Sample (one biological sample in that study)
🔹 SRP = SRA Project (same as study in SRA)
🔹 SRX = SRA eXperiment (library prep linked to a sample)
🔹 SRR = SRA Run (actual FASTQ sequencing run)
🔹 SRS = SRA Sample (internal sample ID in SRA)
🔹 SAMN = BioSample (NCBI sample record)
🔹 PRJNA = BioProject (higher-level project grouping)

👉 Rule of thumb: Start at GSE → see all GSMs
Each GSM links to an SRX
Each SRX contains one or more SRRs (raw FASTQs)

💡 Easy memory hook: M = Member sample (GSM)
X = eXperiment (SRX)
R = Run (SRR)

This mapping saves a lot of time when you want to connect metadata to raw sequencing files.

✅ That's it - simple but powerful. Next time you see a string of IDs, you'll know exactly where it fits. 

#Analysis #Learning #Bioinformatics #AI #SingleCell #Immunology #Research
