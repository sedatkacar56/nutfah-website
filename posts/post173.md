Bismillah, HAVE YOU EVER CONTEMPLATE OVER BASIC GITHUB COMMANDS!!! Yes, you heard me right! Basic commands lines! When you open a new repository on GitHub, it gives you two command-line tips: one for a new repository and one for an existing one. Remember? If not, check the image I shared below.

What attracted my attention were two lines suggested for a new repository: 1️⃣ git branch -M main 2️⃣ git push -u origin main

Let's start with the first one. Why do we need git branch -M main? The rationale behind it is this: in the past, GitHub set the default branch as master (or something else). Today, GitHub's default branch is supposed to be main. So, just in case, we explicitly set the default branch to main.

However, when I generated a repository, the default branch was already main. (UPDATE/ this was wrong!! You have to use and adjust branch to main!!.Otherwise generate another branch n with name of output) There was only one branch from the start — main. So I thought: do we really need to run this command? Maybe I'm wrong. (UPDATE:Yes I was wrong:))Tell me if I am.

Now the second point I want to make is about the -u in:

git push -u origin main

Why do we use -u? Normally, we use:

git push origin main

without -u. I really liked the reason behind it. I didn't know this before! That small -u flag suggested when creating a new repository is basically for memory. It tells Git: "Hey, remember this branch (main) and track it with origin/main. Next time, don't make me write the full command again." After that, you can simply run:

git push

Pretty good, huh? 😄

Doing something blindly and actually knowing what you're doing are two separate things. You out there — yes, I'm talking to you 😊 Whether you use AI or have a stash of working code, learn what you're doing while you're doing it. Thank you! Did you know why we use -u or git branch -M main? Share in the comments 👇

#Git #GitHub #VersionControl #SoftwareDevelopment #Coding #ContinuousLearning #DeveloperMindset #UnderstandDontCopy #AIAssistedCoding #SmallFlagsBigImpact #SingleCell #SingleCellRNAseq #scRNAseq #SpatialTranscriptomics #Bioinformatics #ComputationalBiology #Genomics #Transcriptomics #DataScience #Nextflow #HPC #ReproducibleResearch #Alhamdulillah
