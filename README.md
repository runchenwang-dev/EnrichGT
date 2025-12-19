

# EnrichGT 

> [!WARNING]
> This R package is experimental and exploratory (only proves this idea works). For more rigorous analysis, please use [clusterProfiler](https://bioconductor.org/packages/release/bioc/html/clusterProfiler.html) or [Metascape](https://metascape.org/).


## Install

``` r
install.packages("pak")
pak::pkg_install("ZhimingYe/EnrichGT")
```

Please see the package website for more info: <https://zhimingye.github.io/EnrichGT/>. 


## Acknowledgments

This package is inspired by (but **not** depends on) famous `clusterProfiler`. Without `clusterProfiler`, the team won't try to write this package. 

### If also using `clusterProfiler`

**Please cite:**

T Wu<sup>#</sup>, E Hu<sup>#</sup>, S Xu, M Chen, P Guo, Z Dai, T Feng, L Zhou, W Tang, L Zhan, X Fu, S Liu, X Bo<sup>*</sup>, **G Yu**<sup>*</sup>. clusterProfiler 4.0: A universal enrichment tool for interpreting omics data. ***The Innovation***. 2021, 2(3):100141. doi: [10.1016/j.xinn.2021.100141](https://doi.org/10.1016/j.xinn.2021.100141)



## WorkFlows

``` mermaid

graph LR
    
    M[genes]
    N[genes with weights]
    
    subgraph Enrichment Analysis
        A[egt_enrichment_analysis]
        B[egt_gsea_analysis]
    end

    subgraph Pathway Databases
        D[database_* funcs]
    end

    subgraph Visualize results
        P1[egt_plot_results]
        P2[egt_plot_gsea]
    end

    subgraph egt_recluster_analysis
        K1[Pretty table]
        K2[AI Annotation]
        CC[cluster modules]
        MG[gene modules]
    end

    subgraph Pathway Act. and TF infer 
        
        I[egt_infer]
    end
    
    M --> A
    N --> B
    
    D --> A
    D --> B
    
    A --> C[Enriched Result]
    B --> C

    C --> CC
    C --> MG

    C --> P1

    CC --> K1
    MG --> K1

    CC --> K2
    MG --> K2

    CC --> P1
    C --> P2

    MG --> I


```
