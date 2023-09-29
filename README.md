# commmands

```
cd /workspace

HAL=/workspace/Coleoptera_36-way_20230217.hal

halValidate $HAL

halStats --genomes $HAL > genomes.txt

halStats --tree $HAL> tree.nh

halStats --root $HAL

halStats --bedSequences $genome $HAL > $genome.bed

hal2fasta $HAL $genome --sequence 1 --length 1000000 > $genome.1.1000000.fa

halAlignmentDepth --refSequence 1 --start 0 --length 1000000 --noAncestors --step 1 --outWiggle chr1.0.1000000.wig $HAL $genome

cat chr1.0.1000000.wig | while read line;do awk ‘OFS=“\t”{print 1, NR-1, NR, $line}';done > chr1.0.1000000.bed

halSingleCopyRegionsExtract --refSequence 1 --start 0 --length 1000000 $HAL $genome > $genome.singleCopyRegions.bed

halLiftover --outPSL $HAL $source_genome $source.bed $target_genome $target.bed

hal2maf --refSequence 1 –refGenome $genome –start 0 --length 1000000 --noAncestors --onlyOrthologs $HAL $genome.1.1000000.maf
```





