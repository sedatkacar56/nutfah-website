🤯 Did you know this about Seurat DotPlots?

Have you ever noticed that in Seurat DotPlot, sometimes "Average Expression" is shown on top, and other times "Percent Expressed" is on top — even though you didn't change any code?

Yeah… that's not your mistake 😅

👉 It turns out:
Seurat doesn't lock the legend order in DotPlot
ggplot decides the order internally and that decision can change gene by gene, depending on the data

So the plot is correct, but the legend order can swap unexpectedly.

🔍 Not a bug. To fix it, first decide which you want to see at top?

For Average expression a top do this: lets assign your DotPlot to "p",

p + guides( color = guide_colorbar(order = 1), size = guide_legend(order = 2) )

If you want Percent Expressed at top,

p + guides( size = guide_legend(order = 1), color = guide_colorbar(order = 2) )

🧠 Just ggplot doing its thing behind the scenes. Once you know this, it suddenly makes sense — and you stop doubting yourself every time the legend flips 😄

#Seurat #scRNAseq #DataVisualization #Bioinformatics #ggplot2 #DidYouKnow #Alhamdulillah
