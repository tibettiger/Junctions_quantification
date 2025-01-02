After obtaining bam files for each metacell, we first perform junctions extract and quantification.

junctools=01_junctools
juncstat=02_junc_stat
bamfile=*.bam  //metacell level bamfile; needing .bai index file
output_file=*.junc
${junctools} junctions extract -a 8 -m 50 -s FR ${bamfile} -o ${output_file}
barcode=*.barcode //the cell barcode you want to extract
output=*.stat
${juncstat} ${barcode} ${output_file} ${output}
