
#  AUTOMATIC EXTENSION OF THE ANNOTATION OF THE SNAPDRAGON GENOME

##  DESCRIPTION 

The [Genome Annotation of the Snapdragon Genome V2.0](http://bioinfo.sibs.ac.cn/Am/download_v2.php) included Gene Ontology annotations for 20820 out of 37234 genes (56%). Given that almost half of the genes remained unannotated, we have implemented a method for increasing the number of annotated genes in Antirrhinum majus by using as reference the annotations of the genes of Solanum lycopersicum and Arabidopsis thaliana.

The bioinformatics process followed, through which an extended annotation of the genome was obtained, is described next, obtaining an annotation with 26109 genes annotated (70% of the genome):

- Step 1: Find potential orthologs from Solanum lycopersicum and Arabidopsis thaliana. A best bi-directional hit approach was followed between the genes of the genomes by pairs (Antirrhinum majus vs Solanum lycopersicum and Antirrhinum majus vs Arabidopsis thaliana). The output is a set of candidate pairs of genes from the species compared.

- Step 2: Filtering by e-value. All the results from step 1 with e-value > 0.01 are discarded.

- Step 3: Filtering by identity. All the results with an identity percentage < 60% are discarded.

- Step 4: Filtering by direction. Only those pairs of genes that have passed the previous filters in both directions are kept. This means that if the candidate pair (Gene_X_Antirrhinum_majus ==>Gene_Y_Solanum_lycopersicum) has passed the filters but not the pair(Gene_Y_Solanum_lycopersicum ==> Gene_X_Antirrhinum_majus), then the former is also discarded.

- Step 5: Selection: For each Antirrhinum majus gnene, select the gene from the other species with largest e-value amongst the pairs that have passed the three filters.


##  DATASETS


- [TSV file with the extended annotation of the genome](./files/annotation.tsv)

- [R package with the extended genome annotation for Antirrhinum majus](./files/org.Amajus2.eg.db.zip)
