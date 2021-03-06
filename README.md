# plot_mitochondrial_with_circos
This is a set of hacky scripts which takes a mitochondrial FASTA + annotation from MITOS in BED format, and produces a .svg figure using the CIRCOS plotting tool.

If you have annotation in BED format for another type of circular genome, this should work with relatively minor modifications.

Software dependencies:

1. CIRCOS (http://circos.ca)
2. Seqkit (https://github.com/shenwei356/seqkit) 

Data dependencies / workflow:

1) Get a mitochondrial genome in FASTA format.  You may want to "rotate" the sequence so that the break in the FASTA file is in the AT-rich region (the presumed replication origin for mitochondria)

In my experience, mapping Illumina short reads to a phylogenetically related mitochondrial genome, and assembling with SPAdes works decently.  Your mileage may vary.  If the assembly seems mostly complete, but is perhaps split onto multiple contigs, I'll go in with Bandage (https://rrwick.github.io/Bandage/), and pick the path around the circular assembly graph that is best supported by the coverage.

2) Annotate that mitochondrial genome with the MITOS mitochondrial annotation server http://mitos.bioinf.uni-leipzig.de/index.py

Bernt, M., Donath, A., Jühling, F., Externbrink, F., Florentz, C., Fritzsch, G., Pütz, J., Middendorf, M., and Stadler, P.F. (2013). MITOS: Improved de novo metazoan mitochondrial genome annotation. Molecular Phylogenetics and Evolution 69, 313–319.

3) Append annotation to the BED file for the features that MITOS doesn't support.  Here is an example:

To add features (such as the AT-rich region), you have to add them to your bed file.  See below for an example.  
The "AT-rich" and "IGNOREME" have particular plotting parameters (colored, has text, doesn't have text etc) that are setup in plots.conf

- <code>Photinus_pyralis_mito_genome_v4 15000 16079 AT-rich 0.0 +</code>
- <code>Photinus_pyralis_mito_genome_v4 0 200 IGNOREME  0.0 +</code>
- <code>Photinus_pyralis_mito_genome_v4	2764	3707	TRU	0	+</code>
- <code>Photinus_pyralis_mito_genome_v4	2764	2839	IGNOREME	0	+</code>
- <code>Photinus_pyralis_mito_genome_v4	2840  2915  IGNOREME	0	+</code>
- <code>...</code>

4) Edit the used_commands.txt Bash script to point to the appropriate files.

5) Run the used_commands.txt Bash script, from the directory with the ./*.conf files

6) You may need to edit the various ./*.conf files to get the figure looking how you want it to.  See the CIRCOS documentation.

7) Enjoy your figure:

![alt tag](https://github.com/photocyte/plot_mitochondrial_genome_with_CIRCOS/blob/master/output_example.png)
