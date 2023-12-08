dnanexus_normals_readcount_analysis_v1.1.0
Exome depth is run in two stages. Firstly, read counts are calculated and the second step filers out the CNVs of interest. Read counts are calculated over the entire genome and the CNVs are filtered out using a subpanel BED file.

CNV calling can be performed by providing a readcount file for a set of known normals. 

dnanexus_normals_readcount_analysis_v1.1.0 calculates readcounts for a panel of normals samples intended to use as an input for https://github.com/moka-guys/dnanexus_ED_readcount_analysis

What does the app do?
This app runs the read count calculation stage for a set of known normals.

Using the provided DNANexus project and the list of Pan numbers the app downloads BAMs and BAI.

A Docker image containing Exome depth is downloaded from 001 - The Exomedepth image taken from https://github.com/moka-guys/seglh-cnv/releases/tag/v2.1.0

The readCount.R script is then called, producing a readcount file (normals.RData) 

Inputs
DNAnexus project name where the BAMs and indexes are saved in a folder called '/output'
NOTE: BAM/BAI files need to have a "NORMAL" prefix for the app to recognise it as an input.
Reference_genome (*.fa.gz or *.fa) in build 37
List of comma seperated pan numbers
Bedfile covering the capture region
Optional: panel of normals
Output
normal.RData - Read count data for panel of normals

Created by
This app was created within the Synnovis Genome Informatics section