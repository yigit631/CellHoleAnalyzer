# CellHoleAnalyzer
MATLAB-based tool for counting gaps in cell images and visualizing them with color-coded overlays.
How It Works

Read Image
The input image—either color (RGB) or already grayscale—is loaded using imread.

Convert to Grayscale
If the image is RGB, it’s converted with rgb2gray; otherwise, the original grayscale image is used.

Binarize & Invert
The image is thresholded with imbinarize, then inverted with imcomplement so that cells appear white on a black background.

Noise Removal
Small artifacts are removed using bwareaopen(binaryImage, 50), which deletes connected components smaller than 50 pixels.

Label Connected Components
Each cell is assigned a unique label via bwlabel.

Hole Detection
For each labeled cell, imfill fills its holes; subtracting the original mask reveals the holes, and bwlabel counts them (hc).

Annotation
Bounding boxes and hole counts are overlaid with rectangle and text. A legend explaining the color codes is added via annotation('textbox',…).









