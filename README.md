# HG002.k1—an improved version of the genome benchmark
 
Using the public sequencing data of the reference HG002 cell line, we reconstructed a new version of its diploid benchmark genome—HG002.k1, which greatly improved its quality.

A genome benchmark is a great progress and vital component in the process of evaluating errors in sequencing, de novo assembling, and variant calling instead of previous variant benchmark. The [Genome in a bottle Consortium](https://www.nist.gov/programs-projects/genome-bottle) has played a key role in pioneering the reconstruction of genome benchmarks by assembling and polishing the complete genome of the [HG002](https://www.coriell.org/0/Sections/Search/Sample_Detail.aspx?Ref=GM24385&Product=CC) (GM24385 and huAA53E0) cell line to ensure covering all bases of the HG002 reference material and being perfectly accurate. 

For this goal, the [Genome in a bottle Consortium](https://www.nist.gov/programs-projects/genome-bottle), along with the [Telomere-to-Telomere Consortium](https://sites.google.com/ucsc.edu/t2tworkinggroup) and the [Human Pangenome Reference Consortium](https://humanpangenome.org)  are collaborating on the ["HG002 Q100"](https://github.com/marbl/hg002) project (Q100 means<1 error in 10Gb genome, and thus no errors, while the size of human diploid genome is 6Gb). The consortiums have recently released their updated version of the [HG002 v1.0.1](https://s3-us-west-2.amazonaws.com/human-pangenomics/T2T/HG002/assemblies/hg002v1.0.1.fasta.gz) genome. Except the regions of rDNA clusters, HG002 v1.0.1 is otherwise T2T assembly with a Merqury-estimated QV of 75.1 (Q75.5 on the maternal chromosomes, Q74.7 on the paternal chromosomes). Meanwhile, the consortiums have released all assemblies and raw sequencing data to the public domain (CC0) and encouraged global contributions in building the genome benchmark.

With the available sequencing data, we were able to construct a new assembly—HG002.k1([mat](https://s3.amazonaws.com/hg002.q80/mat.corr2.fasta.gz),[pat](https://s3.amazonaws.com/hg002.q80/pat.corr2.fasta.gz)) —with improved quality that corrects 263 (mat, 116; pat, 147) of the remaining errors present in HG002 v1.0.1, including a 13.653kb deletion in the maternal chromosome 10. Estimated by the same [Merqury](https://github.com/marbl/merqury) software, [code,parameters](https://github.com/KANGYUlab/HG002/blob/main/Merqury-qv.md), and hybrid Hiseq/HiFi database used in other HG002 genome versions, the HG002.k1 genome achieved a Merqury-estimated quality value of 80.83 (Q82.71 on the maternal chromosomes, Q79.49 on the paternal chromosomes). The k1 version is assembled using an in-house developed [verkko](https://github.com/marbl/verkko) -based assembling pipeline, which we have used to build the T2T diploid genome of Han Chinese—T2T-YAO.

## Assembly release and license:
HG002.k1([mat](https://s3.amazonaws.com/hg002.q80/mat.corr2.fasta.gz),[pat](https://s3.amazonaws.com/hg002.q80/pat.corr2.fasta.gz)): a T2T assembly of all 46 chromosomes of HG002 except the rDNA clusters on the acrocentric chromosomes. The assembly was created by applying patches contained in the VCF file hg002v1.0.1_to_hg002.k1([mat](https://github.com/KANGYUlab/HG002/raw/main/mat.pair.vcf.gz),[pat](https://github.com/KANGYUlab/HG002/raw/main/pat.pair.vcf.gz)) to the v1.0.1 assembly and improving the Merqury-estimated QV to Q82.71 (on the maternal side) and Q79.49 (on the paternal side). This Merqury-estimated QV was calculated similarly to that of T2T-CHM13 and T2T-YAO, which has previously been described in detail in McCartney et al. [Chasing perfection: validation and polishing strategies for telomere-to-telomere genome assemblies](https://www.nature.com/articles/s41592-022-01440-3). Nat Methods, 2022.

The assembly sequence is released to the public ([CC0](https://creativecommons.org/publicdomain/zero/1.0/))  and we encourage its reuse. We would appreciate if you would identify any errors in the genome and raise an issue with all relevant information on the associated [issues repository](https://github.com/KANGYUlab/HG002/issues).

## Downloads and sequencing data
Assembly FASTA files of HG002.k1([mat](https://s3.amazonaws.com/hg002.q80/mat.corr2.fasta.gz),[pat](https://s3.amazonaws.com/hg002.q80/pat.corr2.fasta.gz))

[Code for Merqury estimate](https://github.com/KANGYUlab/HG002/blob/main/Merqury-qv.md)

Hybrid Hiseq/HiFi database of HG002 for quality estimation

Sequencing dataset of HG002 and Hybrid Hiseq/HiFi database for quality estimation released by GIAB can be found [here](https://github.com/KANGYUlab/HG002/blob/main/SequencingData.md).

## Contact
Please raise issues on this Github repository concerning access to this dataset. For any errors identified in the assembly itself, please raise issues on the associated [issues repository](https://github.com/KANGYUlab/HG002/issues).

## Related citations:
Rautiainen M, et al. [Telomere-to-telomere assembly of diploid chromosomes with Verkko](https://www.nature.com/articles/s41587-023-01662-6). Nature Biotechnology, 2023.

Nurk, et al. [The complete sequence of a human genome](https://www.science.org/doi/10.1126/science.abj6987). Science, 2022.

He, et al. [T2T-YAO: A Telomere-to-telomere Assembled Diploid Reference Genome for Han Chinese](https://www.sciencedirect.com/science/article/pii/S1672022923001006). Genomics, Proteomics & Bioinformatics, 2023

Zook J. et al. [A robust benchmark for detection of germline large deletions and insertions](https://www.nature.com/articles/s41587-020-0538-8). Nature Biotechnology, 2022.

Wagner, et al. [Curated variation benchmarks for challenging medically relevant autosomal genes](https://www.nature.com/articles/s41587-021-01158-1). Nature Biotechnology, 2022

Jarvis, et al. [Semi-automated assembly of high-quality diploid human reference genomes](https://www.nature.com/articles/s41586-022-05325-5). Nature, 2022 

Rhie, et al. [Merqury: reference-free quality, completeness, and phasing assessment for genome assemblies](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-020-02134-9). Genome Biology, 2020 

McCartney et al., [Chasing perfection: validation and polishing strategies for telomere-to-telomere genome assemblies](https://www.nature.com/articles/s41592-022-01440-3). Nature Methods, 2022.


