## Plot VariantEval Results README

The Plot_VariantEval_results.R script creates plots for a given VariantEval Report. The script creates seven (7) plots, four (4) text files reporting outliers, and a text file containing the VariantEval report for each module included. 

**Usage:**
```
Rscript Plot_VariantEval_results.R <1:Input File> <2:Output Dir> <3:MDS> [4:MDS-derived race calls] [5:Sample Column] [6:MDS Column]
```
  * Input File: Absolute path to VariantEval Report 
     - Note: Merge per chromosome VariantEval Report files using Merge_Variant_Eval_Reports.py script, if merged VariantEval Report file is not available. 
  * Output Directory: Absolute path to output directory
  * MDS: True if adding MDS-dirived race calls file, False otherwise 
  * MDS-derived race calls: (Optional) File name containing sample IDs and MDS-derived race calls
  * Sample Column: (Optional) Header name of column containing sample IDs in MDS file
  * MDS Column: (Optional) Header name of column containing MDS-derived race calls in MDS file

**Seven (7) Plots (*.png* files):** 
1) CompOverlap_concordantRate.png
2) TiTvVariantEvaluator_tiTvRatio.png
3) CountVariants_hetHomRatio.png
4) CountVariants_nSNPs.png
5) CountVariants_nSingletons.png
6) CountVariants_nInsertions_and_nDeletions.png
7) CountVariants_nHets.png <br>
         -  *See examples of these seven plots below*

**Four (4) Files Reporting Outliers:**
1) compOverlap_outliers.txt
2) Outliers_nSNPs_gt2SDs.txt
3) Outliers_nSingletons_gt2SDs.txt
4) Outliers_nHets_gt2SDs.txt

**Examples of Modules Output:**
1) CompOverlap.txt
2) CountVariants.txt
3) TiTvVariantEvaluator.txt
4) IndelSummary.txt

**Example of Seven (7) Plots:**
1) CompOverlap_concordantRate.png <br>

  ![CompOverlap_concordantRate.png](https://preview.ibb.co/g2zTGL/concordant-Rate.png)

2) TiTvVariantEvaluator_tiTvRatio.png

  ![TiTvVariantEvaluator_tiTvRatio.png](https://preview.ibb.co/i1QGmL/ti-Tv-Ratio.png)

3) CountVariants_hetHomRatio.png

  ![CountVariants_hetHomRatio.png](https://preview.ibb.co/kYznt0/het-Hom-Ratio.png)
  
4) CountVariants_nSNPs.png

  ![CountVariants_nSNPs.png](https://preview.ibb.co/j8iY0f/nSNPs.png)

5) CountVariants_nSingletons.png

  ![CountVariants_nSingletons.png](https://preview.ibb.co/dvp1mL/n-Singletons.png)

6) CountVariants_nInsertions_and_nDeletions.png

  ![CountVariants_nInsertions_and_nDeletions.png](https://preview.ibb.co/cUz1mL/n-Insertions-n-Deletions.png)

7) CountVariants_nHets.png

  ![CountVariants_nHets.png](https://preview.ibb.co/fWhFD0/nHets.png)
