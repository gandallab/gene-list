# gene-list

The goal of this repository is to maintain a list of genes implicated in a range of neurodevelopmental and neuropsychiatric disorders. This list was generated from various human genetics study designs—for example, GWAS surveying common variants and whole-exome sequencing (WES) studies surveying rare variants.

## Important files

* [list](list/) - Directory containing downloaded lists.
* [output/risk_genes_brain.tsv](output/risk_genes_brain.txt) - The final merged list.
* [munge-gene-list.Rmd](munge-gene-list.Rmd) An R Markdown document that imports downloaded lists and generates the merged list.

## Sources

|Short name|Desc|Count|Path|Ref|
|:--|:--|--:|:--|:--|
|SFARI|ASD syndromic|328|[SFARI-Gene_genes_01-13-2021release_02-05-2021export.csv](list/SFARI-Gene_genes_01-13-2021release_02-05-2021export.csv)|[SFARI](https://gene.sfari.org/)|
|ASD_Sanders|ASD de novo|65|[mmc7.xlsx](list/mmc7.xlsx)|[Sanders et al. 2015](https://doi.org/10.1016/j.neuron.2015.09.016)|
|ASD_Satterstrom|ASD de novo|102|[Satterstrom.xlsx](list/Satterstrom.xlsx)|[Satterstrom et al. 2020](https://doi.org/10.1016/j.cell.2019.12.036)|
|ASD_Ruzzo|ASD rare inehrited|69|[mmc3.xlsx](list/mmc3.xlsx)|[Ruzzo et al. 2019](https://doi.org/10.1016/j.cell.2019.07.015)|
|DDD|DD de novo|285|[41586_2020_2832_MOESM4_ESM.xlsx](list/41586_2020_2832_MOESM4_ESM.xlsx)|[Kaplanis et al. 2020](https://doi.org/10.1038/s41586-020-2832-5)|
|SCZ_SCHEMA|SCZ rare|10|[meta_results_2021_02_04_20_01_48.csv](list/meta_results_2021_02_04_20_01_48.csv)|[SCHEMA](https://schema.broadinstitute.org/results)|
|SCZ_PsychENCODE|SCZ GWAS PsychENCODE|321|[INT-17_SCZ_High_Confidence_Gene_List.csv](list/INT-17_SCZ_High_Confidence_Gene_List.csv)|[Wang et al. 2018](http://resource.psychencode.org/)|
|SCZ_HiC|SCZ GWAS Hi-C|455|[1-s2.0-S0920996419300891-mmc1.txt](list/1-s2.0-S0920996419300891-mmc1.txt)|[Mah et al. 2018](https://doi.org/10.1016/j.schres.2019.03.007)|
|ASD_ID_DDD_Coe|ASD/ID/DD de novo|253|[41588_2018_288_MOESM3_ESM.xlsx](list/41588_2018_288_MOESM3_ESM.xlsx)|[Coe et al. 2018](https://doi.org/10.1038/s41588-018-0288-4)|
|FMRP|FMRP binding RNA|842|[mmc2.xls](list/mmc2.xls)|[Darnell et al. 2011](https://doi.org/10.1016/j.cell.2011.06.013)|
|CELF4|CELF4 binding RNA|2,803|[mmc2.xls](list/mmc2.xls)|[Wagnon et al. 2012](https://doi.org/10.1371/journal.pgen.1003067)|
|RBFOX|RBFOX1 binding RNA|2,049|[pgen.1003067.s004.xlsx](list/pgen.1003067.s004.xlsx)|[Weyn-Vanhentenryck et al. 2014](https://doi.org/10.1016/j.celrep.2014.02.005)|
|Cancer|Cancer genes|576|[Census_all.tsv](list/Census_all.tsv)|[COSMIC](https://cancer.sanger.ac.uk/census)|
|GenCC|General disease genes|2,754|[gencc-submissions.tsv](list/gencc-submissions.tsv)|[GenCC](https://search.thegencc.org/)|
|Housekeeping|Housekeeping genes|3,804|[HK_genes.txt](list/HK_genes.txt)|[Eisenberg et al. 2013](https://www.tau.ac.il/~elieis/HKG/)|
|MDEM|MDEM|70|[MDEM.txt](list/MDEM.txt)|[Fahrner et al. 2019](https://doi.org/10.1093/hmg/ddz174)|
|UKBB_rare|Disease genes from UKBB WES|564|[41586_2021_4103_MOESM5_ESM.xlsx](list/41586_2021_4103_MOESM5_ESM.xlsx)|[Backman et al. 2021](https://www.nature.com/articles/s41586-021-04103-z)|

## How to add genes

1. Clone this repository, e.g. `git clone git@github.com:gandallab/gene-list.git`.
2. Download a tsv, csv, xlsx, or other tabular data file to the `list` directory.
3. Under Import Data in the Rmd, add a brief code snippet that shows how to import your data and filter it to significant/unique genes.
4. If you want your genes to appear in the output file, add a line that pulls the gene symbol column from your data into the `geneset` list under Combine Data.
5. Add a row to the Markdown table above. Make sure the short name column matches the variable name you chose in R.
6. Push your changes, e.g. `git add .; git commit -m "added genes from [study name]"; git push`.
