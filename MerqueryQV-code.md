Generating k-mer databases
```
meryl count k=21 threads=24 memory=120 output son_ngs.k21.meryl son.ngs.fastq.gz
meryl count k=21 threads=24 memory=120 output son_hifi.k21.meryl hifi.fq.gz
```
Excluding k-mers occurring only once in each database
```
meryl greater-than 1 son_hifi.k21.meryl output son_hifi.k21.gt1.meryl
meryl greater-than 1 son_ngs.k21.meryl output son_ngs.k21.gt1.meryl

```
Matching the diploid (2-copy) peak to 35x
```
meryl divide-round 2 son_ngs.k21.gt1.meryl output son_ngs.k21.gt1-div2.meryl
meryl increase 3 son_ngs.k21.gt1-div2.meryl output son_ngs.k21.gt1-div2-add3.meryl

meryl divide-round 4 son_hifi.k21.gt1.meryl output  son_hifi.k21.gt1-div4.meryl
meryl increase 2 son_hifi.k21.gt1-div4.meryl output son_hifi.k21.gt1-div4-add2.meryl 
```
union the two dbs and set the frequency to the maximum observed in the two datatypes
```
meryl union-max son_ngs.k21.gt1-div2-add3.meryl son_hifi.k21.gt1-div4-add2.meryl  output son_ngs.hybrid.meryl
```

Running Merqury
```
$MERQURY/trio/hapmers.sh mat_ngs.k21.meryl pat_ngs.k21.meryl son_ngs.hybrid-final-2.meryl
merqury.sh son_ngs.hybrid.meryl mat_ngs.k21.hapmer.meryl pat_ngs.k21.hapmer.meryl hg002.mat.fasta hg002.pat.fasta hg002-QV

```
