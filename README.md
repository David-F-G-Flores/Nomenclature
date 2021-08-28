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
