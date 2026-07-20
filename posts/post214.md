🧬 A common misconception: pip install is not actually a Python command. When you run it, you're talking to your system's shell (Terminal, PowerShell, etc.) — not the Python interpreter.

This explains why pip install pandas fails inside Python scripts but works in the terminal.

# ✅ In the terminal/shell
pip install pandas

# ✅ Within Python environments (recommended)
python -m pip install pandas

# ❌ This won't work inside a .py script
import subprocess
pip install pandas  # SyntaxError

In tools like Jupyter and Quarto, each code chunk runs a specific language engine. Package installation is an environment setup step — not analysis code. Mixing them causes errors.

Two distinct phases:
1. pip install — environment setup phase (outside Python)
2. import pandas — actual Python code (inside your script)

🧠 Think of pip as the tool that stocks your pantry. import is the step where you cook. They happen in different places.

#Python #DataScience #Programming #Bioinformatics #pip #Jupyter #Quarto
