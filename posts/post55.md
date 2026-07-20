📚 Share Your R Library Across Computers with .libPaths() + OneDrive + robocopy

Tired of reinstalling 50+ R packages every time you switch computers or get a new machine? Here's how to set up a shared R library:

Part 1: Point R to a shared library location using .libPaths()

# In your .Rprofile (runs every R session)
# Add a shared library path at the TOP of the list
.libPaths(c(
  "C:/Users/username/OneDrive/R_Library/4.3",  # Shared library
  .libPaths()  # Keep default paths as fallback
))

# Verify the paths
.libPaths()

# Install packages to the shared library
install.packages("Seurat", lib = "C:/Users/username/OneDrive/R_Library/4.3")

Why OneDrive? It syncs automatically across all your Windows machines. Once set up, your entire R library travels with you.

---

Part 2: Keep the library synced with robocopy (for larger libraries or HPC)

# Windows CMD / PowerShell — sync R library to a network drive
robocopy "C:\Users\username\OneDrive\R_Library\4.3" `
         "\\server\shared\R_Library\4.3" `
         /MIR /Z /W:5 /R:3

# Options explained:
# /MIR = Mirror: sync additions AND deletions
# /Z = Restartable mode (handles network interruptions)
# /W:5 = Wait 5 seconds between retries
# /R:3 = Retry 3 times on failure

# To sync only new/changed files (safer)
robocopy "C:\Users\username\OneDrive\R_Library\4.3" `
         "\\server\shared\R_Library\4.3" `
         /E /Z /XO

✅ Benefits:
- Install once, use everywhere
- No more "package not found" on a new machine
- Works with OneDrive, Dropbox, or any network share
- robocopy handles large libraries (Seurat + dependencies = 2GB+) reliably

⚠️ Match R versions: keep separate library folders per R version (4.2, 4.3, etc.)

#RStats #RProgramming #OneDrive #robocopy #Bioinformatics #Productivity #Workflow #WindowsTips
