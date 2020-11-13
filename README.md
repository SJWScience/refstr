# refstr
Analysis stuff - problem solving and codes

------------------------------------------

### Example call

```
grep -E '#CHROM' -A 99999999 ${1}_L001_R2_001.vcf | awk 'print{$1 $2 $4 $5}' > ${1}_L001_R2_001.vcf.temp
mv  ${1}_L001_R2_001.vcf.temp  ${1}_L001_R2_001.vcf
sed '/>/d' genome.fasta | tr -d '\n' > reference_1line_noheader.fasta

header=$(head -n 1 genome.fa | sed "s/^>//g")

bash refstr/refstr.sh ${1}_L001_R2_001.vcf reference_1line_noheader.fasta reference.gtf ${1}_L001_R2_001 "$header" 8 $line_length
```
