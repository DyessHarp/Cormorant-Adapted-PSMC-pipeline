# Cormorant Genomic Pipeline for PSMC Analysis

This repository outlines the pipeline used to convert different cormorant genomes in order to be used for the PSMC (Pairwise Sequentially Markovian Coalescent) method and demographic reconstructions.

## Historical Demographic History

The PSMC (Pairwise Sequentially Markovian Coalescent) model allows the reconstruction of changes in effective population size (*Ne*) over time from the diploid genome of a single individual. Based on coalescent theory, this model uses the distribution of heterozygosity across the genome to infer past demographic events such as bottlenecks and population expansions (Li & Durbin, 2011). This approach is especially useful for wild species with limited historical records, as it enables linking variations in population size to significant paleoclimatic events.

We selected a genome with medium coverage (~20×) for the reconstruction of demographic history using the PSMC model. The analysis followed an adapted pipeline available in this repository. Quality control was performed with **FastQC** and summarized using **MultiQC**. Adapter sequences and low-quality regions were removed with **Trimmomatic**. Clean reads were then aligned to the *Phalacrocorax carbo* reference genome (NCBI accession: GCA_963921805.1) using **BWA-MEM**. The resulting BAM files were sorted and indexed with **SAMtools**. **BCFtools** was used to generate PSMC-compatible diploid FASTA files. Finally, **PSMC** (v. *insert version*) was run with the following optimized parameters:

