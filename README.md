# R scripts used in the study "Patterns of gene co-expression under water-deficit treatments and pan-genome occupancy in Brachypodium distachyon"


These scripts are part of the study titled: Patterns of gene co-expression under water-deficit treatments and pan-genome occupancy in Brachypodium distachyon.
Authors: Rubén Sancho, Pilar Catalán, Bruno Contreras-Moreira, Thomas E. Juenger, David L. Des Marais


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

# 4) Run WGCNA to compute the connectivities

Rscript -e "rmarkdown::render('05a_WGCNA_kdiff_mean_D_script.Rmd',output_file='05a_WGCNA_kdiff_mean_D_script.html')" &> 05a_WGCNA_kdiff_mean_D_script.out &
Rscript -e "rmarkdown::render('05b_WGCNA_kdiff_mean_W_script.Rmd',output_file='05b_WGCNA_kdiff_mean_W_script.html')" &> 05b_WGCNA_kdiff_mean_W_script.out &

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


