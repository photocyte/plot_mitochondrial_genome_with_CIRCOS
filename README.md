# plot_mitochondrial_with_circos
This is a set of hacky scripts which goes from mitochondrial FASTA + annotation from MITOS, to figure using the CIRCOS plotting tool.

You need:
1) A mitochondrial genome in FASTA format
   - In my experience, mapping Illumina short reads to a phylogenetically related mitochondrial genome, and assembling with SPAdes, works decently.  Your mileage may vary.  Here is my one-liner that does it.
   
