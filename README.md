# Run Deep Learning model prediction on large images 

This notebook tries to solve Out Of Memory (OOM) error when trying to run Deep Learning (or any other) models on large images.

OOM is avoided by:
    
    Cutting large image to smaller rectangle chunks 
    Run prediction on chunks 
    Assemble large image from chunks

Chunks have width, height, and also border. Borders cause chunks to have overlapping regions. 
While reconstructing, borders are removed partially or completely to avoid incorrect predictions near borders. 
If borders are removed partially, assembling chunks will have overlapping. In the region where images overlap predictions are averaged, that way there is a smooth transition between chunks.
