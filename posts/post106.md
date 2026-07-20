💡 I was looking for my shell script belonging to a certain FASTQ file… I needed to find which .sh file mentioned a specific dataset tag, so I ran: 

grep -r --include = "*.sh" "Chrm_777_FLEX20_Mouse_24plex_GEMX_July2025" .

But instead of getting results, I got this error: 

grep: Chrm_777_FLEX20_Mouse_24plex_GEMX_July2025: No such file or directory

Everything looked right — until I realized the problem was just a single space between --include and =. 

✅ Correct command: 

grep -r --include="*.sh" "Chrm_777_FLEX20_Mouse_24plex_GEMX_July2025" .

Once I removed that space, grep searched all .sh scripts recursively and worked perfectly. Tiny syntax detail — big difference. In Linux, spaces matter. 

🧠 Recap 
- -r → recursive search through folders
- --include="*.sh" → only .sh (shell) scripts 
- . → start search from current directory 

💬 Ever debugged for 10 minutes just to realize it was a space? 😅 

#BashScripting #InSilicoResearch #CommandLine #UnixTips #MachineLearning #Linux #Automation
