💻 Shell Tip – Stop Repeating Yourself! One of the best habits in bash (or Linux shell) is to store things in variables instead of typing them again and again. For example, instead of copying this long DOI ID each time: 

DOI_ID="45.678/DVN/SHELLTIP" 

You can just call it back with: 

echo $DOI_ID 

But here's the trick: 

$VAR → quick and common 
${VAR} → safer when your variable sits next to other text 

Example: 

FILENAME="${DOI_ID}_results.txt" 

Without {}, the shell might think the variable name is DOI_ID_results (which doesn't exist). With {}, there's no confusion. 

#Research #Automation #HPC #Macros #AutomationTips #Networking
