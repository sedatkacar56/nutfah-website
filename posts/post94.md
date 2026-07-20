📌 Shell Tip – Quotes Matter! Single vs. double quotes can completely change what happens with your variables. 

👉 Double quotes " " → variables expand 
NAME="Sedat "
echo "Hello $NAME "
# Output: Hello Sedat 

👉 Single quotes ' ' → variables are literal 
NAME="Sedat" 
echo 'Hello $NAME' 
# Output: Hello $NAME 

Rule of thumb: Use " " when you want variable expansion. Use ' ' when you want to protect the text from being expanded or interpreted. 

This small detail prevents a lot of headaches when scripting! 

#YAML #Automation #HPC #AI #Knowledge #Innovation #Macros #doublequotes #singlequotes
