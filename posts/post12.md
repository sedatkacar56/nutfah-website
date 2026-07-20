🚫 You loop through genes to plot with Seurat::FeaturePlot()... Everything works — until one gene is missing. Boom 💥 Error. Your whole script stops. But why stop the show for one gene? Here's how I catch the error and keep moving 👇

tryCatch({
  << what you wanna do >>
  FeaturePlot(seurat_obj, features = "Trouble_maker") |> print()
}, error = function(e) {
  message("⚠️ Skipped: ", e$message)
} )

💡 Don't stop on the first error. Catch it. Report it. Move on.

#rstats #Seurat #bioinformatics #ErrorHandling #SingleCell #DataScience
