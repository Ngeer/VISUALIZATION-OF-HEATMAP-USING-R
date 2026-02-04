# VISUALIZATION-OF-HEATMAP-USING-R
The heatmap were created from using R programing and was mainly used in the analysis of AMR
# heatmap.R
# Update setwd() to point to the folder containing your CSV file
setwd('C:\\Users\\Stuart\\Downloads') # change this to your working directory

# Replace "PRODUCT VS CLASSIFICATION.csv" with your CSV filename (first column used as row names)
data <- read.csv("PRODUCT VS CLASSIFICATION.csv", header = TRUE, row.names = 1)

library(pheatmap)

# Define the color palette
color_palette <- colorRampPalette(c("black", "green", "red"))(50)

# Create PNG output (saved in working directory)
png("PRODUCT VS CLASSIFICATION.png", width = 20000, height = 20000, res = 800)

pheatmap(
  data,
  cluster_rows = FALSE,
  cluster_cols = FALSE,
  color = color_palette,
  fontsize_row = 15,
  fontsize_col = 15,
  cellwidth = 40,
  cellheight = 15,
  border_color = 'white',
  na_col = "black"
)

dev.off()
