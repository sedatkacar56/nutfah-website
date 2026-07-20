🔍 Can't Remember the Exact R Function Name? Use apropos()!

Ever know what a function does but forget its exact name? apropos() searches all loaded packages for functions matching your pattern:

# Find functions related to "merge"
apropos("merge")
# [1] "merge"        "merge.data.frame"  "merge.default"

# Case insensitive search
apropos("cluster", ignore.case = TRUE)

# Use regex patterns
apropos("^Find")  # Functions starting with "Find"

# Search across all installed packages (slower)
apropos("Neighbors", where = TRUE)

✅ Perfect for when you know part of a function name but can't recall the rest — especially useful in Seurat where functions like FindNeighbors, FindClusters, FindMarkers all share prefixes.

Pro tip: Combine with help.search() for even broader searching.

#RStats #RProgramming #Bioinformatics #RTips #Seurat #SingleCell
