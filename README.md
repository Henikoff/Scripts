Data processing for "Superabundant microRNAs are expressed from human ribosomal RNA promoters insulated by CTCF"
Software required:
SRA-Toolkit
Kent_tools
samtools
bedtools
cutadapt
bowtie2

A. Download fastq files from SRA: sra_download.csh

B. Single-end read processing to make bed files of mapped fragments
1. Trim adapters: cutadapt_se.csh
2. Align to reference sequence with bowtie2: bowtie_se.csh

C. Paired-end read processing to make bed files of mapped fragments
1. Trim adapters: cutadapt_pe.csh
2. Align to reference sequence with bowtie2: bowtie_pe.csh (calls bamtobed_strand.csh, fixn.csh)

D. Make bigwig tracks of normalized counts
1. norm_beds.csh (calls fraction_norm.csh)

E. Accumulate normalzed counts over sites
1. Convert bigwig files to bedgraph format for bedtools: bw2bg.csh
2. Make text files suitable for use by degust: wao.csh (calls mult_two_cols.pl and avg.pl)
