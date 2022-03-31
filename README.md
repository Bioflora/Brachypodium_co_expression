# R scripts used in the study "Patterns of gene co-expression under water-deficit treatments and pan-genome occupancy in Brachypodium distachyon"


These scripts are part of the study titled: Patterns of gene co-expression under water-deficit treatments and pan-genome occupancy in Brachypodium distachyon.

Authors: Rubén Sancho 1,2, Pilar Catalán 1,2,3, Bruno Contreras-Moreira 2,4,5, Thomas E. Juenger 6, David L. Des Marais 7

Affiliations:

1. Department of Agricultural and Environmental Sciences, High Polytechnic School of Huesca, University of Zaragoza, Huesca, Spain
2. Grupo de Bioquímica, Biofísica y Biología Computacional (BIFI, UNIZAR), Unidad Asociada al CSIC, Spain
3. Tomsk State University, Tomsk, Russia
4. Estación Experimental de Aula Dei-Consejo Superior de Investigaciones Científicas, Zaragoza, Spain
5. Fundación ARAID, Zaragoza, Spain
6. Department of Integrative Biology, The University of Texas at Austin, Austin, TX. USA
7. Department of Civil and Environmental Engineering, Massachusetts Institute of Technology, Cambridge, MA. USA


# 1) Run WGCNA to filter and prepare the data set

Conditions D (Drought) and W (Water-control)

I used Sleuth package to compute the normalized TPMs using 01_Sleuth_script.Rmd. This is the input for the next step using WGCNA package
```
Rscript -e "rmarkdown::render('02_WGCNA_data_input_prep_script.Rmd',output_file='02_WGCNA_data_input_prep_script.html')" &> 02_WGCNA_data_input_prep_script.out &
```

# 2) Run WGCNA to compute the soft-power

```
Rscript -e "rmarkdown::render('03a_WGCNA_soft_power_D_script.Rmd',output_file='03a_WGCNA_soft_power_D_script.html')" &> 03a_WGCNA_soft_power_D_script.out &
Rscript -e "rmarkdown::render('03b_WGCNA_soft_power_W_script.Rmd',output_file='03b_WGCNA_soft_power_W_script.html')" &> 03b_WGCNA_soft_power_W_script.out &
```

# 3) Run WGCNA to compute the networks

```
Rscript -e "rmarkdown::render('04a_WGCNA_net_D_unsigned_script.Rmd',output_file='04a_WGCNA_net_D_unsigned_script.html')" &> 04a_WGCNA_net_D_unsigned_script.out &
Rscript -e "rmarkdown::render('04b_WGCNA_net_W_unsigned_script.Rmd',output_file='04b_WGCNA_net_W_unsigned_script.html')" &> 04b_WGCNA_net_W_unsigned_script.out &
```

# 4) Run WGCNA to compute the connectivities

```
Rscript -e "rmarkdown::render('05a_WGCNA_kdiff_mean_D_script.Rmd',output_file='05a_WGCNA_kdiff_mean_D_script.html')" &> 05a_WGCNA_kdiff_mean_D_script.out &
Rscript -e "rmarkdown::render('05b_WGCNA_kdiff_mean_W_script.Rmd',output_file='05b_WGCNA_kdiff_mean_W_script.html')" &> 05b_WGCNA_kdiff_mean_W_script.out &
```

# 5) Compute hub nodes (threshold 0.90), MM and others

```
Rscript -e "rmarkdown::render('06a_WGCNA_hub_D_threshold090_script.Rmd',output_file='06a_WGCNA_hub_D_threshold090_script.html')" &> 06a_WGCNA_hub_D_threshold090_script.out &
Rscript -e "rmarkdown::render('06b_WGCNA_hub_W_threshold090_script.Rmd',output_file='06b_WGCNA_hub_W_threshold090_script.html')" &> 06b_WGCNA_hub_W_threshold090_script.out &
```

If you want to know the "top hub nodes" run: 06c_WGCNA_top_hubs_D_script and 06d_WGCNA_top_hubs_W_script

# 6) Comnpute consensus data set and net

```
Rscript -e "rmarkdown::render('07_WGCNA_consensus_data_script.Rmd',output_file='07_WGCNA_consensus_data_script.html')" &> 07_WGCNA_consensus_data_script.out &
Rscript -e "rmarkdown::render('08_WGCNA_consensus_net_script.Rmd',output_file='08_WGCNA_consensus_net_script.html')" &> 08_WGCNA_consensus_net_script.out &
```

# 7) Compare Consensus vs Drought modules, and Consensus vs Water modules using WGCNA

```
Rscript -e "rmarkdown::render('09a_WGCNA_compare_modules_D_script.Rmd',output_file='09a_WGCNA_compare_modules_D_script.html')" &> 09a_WGCNA_compare_modules_D_script.out &
Rscript -e "rmarkdown::render('09b_WGCNA_compare_modules_W_script.Rmd',output_file='09b_WGCNA_compare_modules_W_script.html')" &> 09b_WGCNA_compare_modules_W_script.out &
```

# 8) Run NetRep package to check the preservation among the modules

```
Rscript -e "rmarkdown::render('10_NetRep_script.Rmd',output_file='10_NetRep_script.html')" &> 10_NetRep_script.out &
```

All modules are preserved

# 9) Differential expression genes

This analysis was compted using Sleuth package. See script 01_Sleuth_script.Rmd



# Excel files (Supplementary Files)

File S1. Expression of filtered and normalized (by Sleuth package) TPM (transcripts per million) of the 4,941 differentially expressed (DE) isoforms (3,489 DE genes) under the water (W) and drought (D) conditions. The averages TPM per treatment for each isoform and their differences between Drought and Water treatments were computed.

File S2. Summary annotation of the 4,941 differentially expressed (DE) isoforms (3,489 DE genes) under drought (D) and water (W) conditions. Isoform (B. distachyon_314_v3.1 (Bd21 accession) reference transcriptome); regulation under drought condition compared to water condition; occupancy (core (33 accessions), soft-core (31-32 accessions) and shell (≤30 accessions)); matched Drought and Water modules (numeric identification of the module where the DE isoforms were assigned to); DE hub node (DE genes detected such as hub gene in the Drought (D) or Water (D) modules); Pfam, KEGG/ec, GO annotations; arabi-defline and rice-defline (annotation in Arabidopsis and rice).

File S3. Detailed statistics of the enrichment analysis according to the statistically significant GO biological process detected for the genes (all, core, soft-core and shell genes) clustered in the Drought (D) and Water (W) modules applying the statistical overrepresentation test of Panther (http://pantherdb.org/) tool and sorted by the lowest FDR. Every tab corresponds to the all, core, soft-core or shell genes results for each module (e.g. D_1: enrichment results for all genes of the Drought module 1; D_1_core: enrichment results for the core genes of the Drought module 1; …). There are not tabs for the “No statistically significant results”. The headers of the table correspond to Ref-list (number of genes of the reference Brachypodium distachyon list (34,230 genes) from Ensembl source that map to this particular annotation data category); Client Text Box Input (number of genes in the query uploaded list that map to this particular annotation data category); expected (number of genes you would expect in your list for this category, based on the reference list); +/- (A plus/minus sign indicates over/under-representation of this category in your experiment (you observed more/fewer genes than expected based on the reference list for this category)); fold Enrichment (genes observed in the uploaded list with respect to the expected genes (number of genes in the query list divided by the expected number of genes): > 1, the category is overrepresented , and <1, the category is underrepresented in the experiment; raw p-value (determined by Fisher’s exact test; probability that the number of genes observed in this category occurred by chance (randomly), as determined by the reference list); False Discovery Rate (FDR) (by default a critical value of 0.05 is used to filter results, therefore all results shown are valid for an overall FDR<0.05 even if the FDR for an individual comparison is greater than that value).
