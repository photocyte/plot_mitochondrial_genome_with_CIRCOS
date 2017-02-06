# plot_mitochondrial_with_circos
This is a set of hacky scripts which goes from mitochondrial FASTA + annotation from MITOS, to figure using the CIRCOS plotting tool.

You need:

1) A mitochondrial genome in FASTA format

In my experience, mapping Illumina short reads to a phylogenetically related mitochondrial genome, and assembling with SPAdes, works decently.  Your mileage may vary.  Here is my one-liner that does it.

2) Annotate that mitochondrial genome with the MITOS mitochondrial annotation server http://mitos.bioinf.uni-leipzig.de/index.py

Bernt, M., Donath, A., Jühling, F., Externbrink, F., Florentz, C., Fritzsch, G., Pütz, J., Middendorf, M., and Stadler, P.F. (2013). MITOS: Improved de novo metazoan mitochondrial genome annotation. Molecular Phylogenetics and Evolution 69, 313–319.

   
