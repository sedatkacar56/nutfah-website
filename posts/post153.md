I did an analysis in the past. You forgot where is the slurm job batch file.

-hints: you know the directory where it is, and you know the file type (.sh)
-try to remember only one keyword. and then rest is Bobs your uncle!

Here you go:

First one:
grep -r "--mode inqc" --include="*.sh" .

Second one:
find . -name "*.sh" -exec grep "--mode inqc" {} +

Both search the files and their content if they have this keyword. Both worked for me. The first one giving colorful, attracting outcome.

Literally it says find any .sh file that contains the literal text --mode inqc, which you can change based on what u remember file contains.

#ssh #linuxshell #bash #slurmjob #hpc #search #lostfile #forgetting
