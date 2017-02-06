# plot_mitochondrial_with_circos
This is a set of hacky scripts which goes from mitochondrial FASTA + annotation from MITOS in BED format, to a .svg figure using the CIRCOS plotting tool.

If you have annotation in BED format for another type of circular genome, this should work with relatively minor modifications.

Software dependencies:
1) CIRCOS (http://circos.ca)
2) Seqkit (https://github.com/shenwei356/seqkit) 

Data dependencies / workflow:

1) Get a mitochondrial genome in FASTA format

In my experience, mapping Illumina short reads to a phylogenetically related mitochondrial genome, and assembling with SPAdes works decently.  Your mileage may vary.  If the assembly seems mostly complete, but is perhaps split onto multiple contigs, I'll go in with Bandage (https://rrwick.github.io/Bandage/), and pick the path around the circular assembly graph that is best supported by the coverage.

2) Annotate that mitochondrial genome with the MITOS mitochondrial annotation server http://mitos.bioinf.uni-leipzig.de/index.py

Bernt, M., Donath, A., Jühling, F., Externbrink, F., Florentz, C., Fritzsch, G., Pütz, J., Middendorf, M., and Stadler, P.F. (2013). MITOS: Improved de novo metazoan mitochondrial genome annotation. Molecular Phylogenetics and Evolution 69, 313–319.

3) Edit the used_commands.txt Bash script to point to the appropriate files.

4) Run the used_commands script, from the directory with the ./*.conf files

5) You may need to edit the various ./*.conf files to get the figure looking how you want it to.
