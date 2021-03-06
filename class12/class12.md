Class 12: Structural bioinformatics pt. 1
================

## PDB Statistics

Here we inspect the types of structures in the main database

> Q1: Download a CSV file from the PDB site (accessible from “Analyze”
> -\> “PDB Statistics” \> “by Experimental Method and Molecular Type”.
> Move this CSV file into your RStudio project and determine the
> percentage of structures solved by X-Ray and Electron Microscopy.

``` r
#Read in file
stats <- read.csv("Data Export Summary.csv", row.names=1)


#calculate percentage values asked for
ans <- (stats$Total/sum(stats$Total))*100
names(ans) <- rownames(stats)
round(ans,2)
```

    ##               X-Ray                 NMR Electron Microscopy               Other 
    ##               88.95                8.04                2.72                0.19 
    ##        Multi Method 
    ##                0.10

> Q2: Also can you determine what proportion of structures are protein?
> Aim to have a rendered GitHub document with working code that yields
> your answers.

``` r
round((sum(stats$Proteins)/sum(stats$Total))*100, 2)
```

    ## [1] 92.69

> Q3: Type HIV in the PDB website search box on the home page and
> determine how many HIV-1 protease structures are in the current PDB?

1289
