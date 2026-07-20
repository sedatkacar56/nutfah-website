⚙️ Customize Your R Startup with .Rprofile — Run Code Every Time R Starts

Did you know R automatically runs .Rprofile at startup? Use it to pre-load packages, set options, create shortcuts, and save time every session.

# Open or create your .Rprofile
file.edit("~/.Rprofile")

# Example .Rprofile contents:

# Auto-load common packages
if (interactive()) {
  suppressMessages({
    library(dplyr)
    library(ggplot2)
  })
}

# Set CRAN mirror
options(repos = c(CRAN = "https://cloud.r-project.org"))

# Custom shortcuts
options(scipen = 999)         # Disable scientific notation
options(stringsAsFactors = FALSE)  # Modern default

# Useful custom functions
qplot <- function(x) head(x, 10)  # Quick preview

✅ Key tips:
- Use interactive() check to avoid running code in scripts
- Keep it lightweight — heavy packages slow startup
- Use suppressMessages() to keep the console clean
- Project-specific .Rprofile in project directory overrides global

💡 For bioinformatics: add your most-used packages (Seurat, dplyr, ggplot2) and set options(future.globals.maxSize) for large parallel operations.

#RStats #RProgramming #RProfile #Bioinformatics #Productivity #RTips
