# Nomenclature
To change various genetic nomenclature

Load relevant genome assemblies

```R
library(biomaRt)

cowinfo <- useEnsembl(biomart = "ensembl", 
                      dataset = "btaurus_gene_ensembl", 
                      version = "94")



snpmart <- useEnsembl(biomart = "ENSEMBL_MART_SNP", 
                      dataset = "btaurus_snp", 
                      version = "94")

```

If filters need to be changed e.g. ```"external_gene_name"```  to ENSEMBL gene name


Create vector of genes and loop over
```R
mousegenes2 <- c('ASS1','ATP2A1','SLC6A5','SLC4A2','AXL4','KDM2B','APAF1','SMC2','GART','CWC15','BCKDHA','MTCL1','PPP1R13L','PNPLA6','MANBA','MAN2B1')


for (genes in mousegenes2){
  print(genes)
  data = getBM( attributes=c("external_gene_name","ensembl_gene_id","btaurus_homolog_associated_gene_name","description","btaurus_homolog_orthology_confidence"), filters= ("external_gene_name"), values =genes,mart=cowinfo)
  btauLr[[genes]] <- data
}

```

