🔌 detach() vs. unloadNamespace() — How to Actually Free Memory from R Packages

Loading many large bioinformatics packages can eat all your RAM. Here's how to unload them when you're done:

# detach() — removes from search path (but keeps namespace in memory)
detach("package:ggplot2", unload = TRUE)

# unloadNamespace() — fully removes namespace from memory
unloadNamespace("ggplot2")

# The RIGHT way to fully unload a package:
detach("package:Seurat", unload = TRUE)
unloadNamespace("Seurat")
gc()  # Garbage collect after unloading

# Check what's currently loaded
search()           # Search path
loadedNamespaces() # All loaded namespaces

# Unload all non-base packages (nuclear option)
pkgs <- names(sessionInfo()$otherPkgs)
if (!is.null(pkgs)) {
  invisible(lapply(paste0("package:", pkgs),
                   detach, character.only = TRUE, unload = TRUE))
}

⚠️ Key differences:
- detach() removes the package from the search path (you can't use its functions directly) but may keep the namespace loaded
- unloadNamespace() goes deeper — removes the namespace from memory
- Some packages can't be fully unloaded due to C-level bindings

💡 For Seurat specifically: it's often easier to restart R than to unload it cleanly. Use RStudio's "Restart R" or .rs.restartR().

#RStats #MemoryManagement #RProgramming #Seurat #Bioinformatics #Productivity #Packages
