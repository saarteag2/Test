## Transmission Summary README

**Goal:**
The goal of this script is to create a flat file and family aggregation file. The flat file is a tab-delimited file with one row per variant per child and 22 columns. The family aggregation file is a tab-delimited file with one row per variant per family and 39 columns. In order to create these output files, the script requires two inputs: (1) a ped file with family information and (2) an "inheritance patterns" file as input. This script reformats the inheritance pattern file and parses its INFO field in order to create the flat file and family aggregation file. Note: These files are subsequently split into small files for annotation, annotated (adding additional columns), and then ready for filtering (https://github.com/dhglab/bmap_scripts/tree/master/annotate_transmission_summary). 

**Usage:**
```
/usr/local/anaconda2/bin/python /ifs/collabs/geschwind/NGS/NGS_analyses/iHART_genomes/code/make_transmission_flat_db.py <input_file INPUT_FILE > <--out_dir OUT_DIR> <prefix Prefix> <suffix Suffix> [--alt_ped_file ALT_PED_FILE] [--family_only Yes|No] [--SV Yes|No]
```
*	<input_file>: The absolute path to the inheritance patterns file to use (Required) <br>
*	<--out_dir>: The absolute path to the output directory (Required) <br>
*	< prefix >: The prefix for the output files, defaults to AGRE_transmission.flat (Required) <br>
*	< suffix >: The suffix for output files (e.g., "chr1" or "SVs") (Required) <br>
*	[--alt_ped_file]: An alternate ped file. The default ped is /ifs/collabs/geschwind/NGS/NGS_analyses/iHART_genomes/November2015_Analysis/2308passedQC.ped (Optional) <br>
    - Note: This script expects the .ped file to have a header line== 'IID', 'ID', 'Sex', 'Maternal', 'Paternal', 'Phenotype' <br>
*	[--family_only]: Omit non-family outputs "Yes" or "No". In bash script must also specify "Yes" or "No" for --SV if using (Optional) <br>
    -	Option to exclude the flat db output <br>
*	[--SV]: The input file is structural variants "Yes" or "No" <br>
    -	Must also specify "Yes" or "No" for --family_only if using. <br>


**Flat File Columns:**

| Column Number| Column Name| Column Description|
| --- | --- | --- | 
|1| Chr | chromosome|
|2| Position | position within chromosome|
|3| Endpos | end position, if applicable|
|4| Ref | reference allele|
|5| Alt | alternate allele|
|6| esp6500siv2_all | alternate allele frequency based on all ethnicities provided in the NHLBI Exome Sequencing Project|
|7| ExAC_ALL | alternate allele frequency based on all ethnicities provided in ExAC?|
|8| 1000g2015aug_all | alternate allele frequency based on all ethnicities provided in 1000G, Aug 2015 (http://www.1000genomes.org/)|
|9| cg46 | alternate allele frequency based on 46 unrelated samples sequenced and processed with the Complete Genomics pipeline|
|10| CADD | raw CADD score (deleterious-ness of the SNP/inDEL)|
|11| CADD_Phred | scaled score (1-99) * We limited this (due to data size and interest) to the top 10% of deleterious variants recieving a score. Thus, the max score listed will be 10. |
|12| Polyphen2_HDIV_score | the score that Polyphen2 gives the snp based on the HumDiv database.  usually NA in this file|
|13| Polyphen2_HDIV_pred | B/D/P (benign/damaging/possibly damaging)|
|14| Polyphen2_HVAR_score | the score that polyphen2 gives the snp based on the HumVar database.  usually NA in this file|
|15| Polyphen2_HVAR_pred | B/D/P (benign/damaging/possibly damaging)|
|16| consequence | Predicted variant functional consequence as determined by Variant Effect Predictor (VEP) (i.e. synonymous_variant,stop_gained,stop_lost,frameshift_variant,splice_acceptor_variant,splice_donor_variant)|
|17| gene_symbol | code for gene|
|18| family | family id number|
|19| child_id | sample number *Participant ID (from AGRE cohort) only chidren are listed in the flat files since the genotype of the parents can be inferred (and was previously determined) by the inheritance pattern).|
|20| is_aff | boolean (assuming 1 is affected and 0 is not?)|
|21| inheritance_type | newly_homozygous, hemizygous (filtered for these two types only)|
|22| Info | LOTS of information here which we chose to annotate. It provides the source information for many of the other separated columns (e.g., consequence, Polyphen, 1000g).|

**Family Aggregation File Columns:**

| Column Number| Column Name| Column Description| Column Formula (If Applicable)|
| --- | --- | --- | --- |
|1| Chr| chromosome|
|2| Position| position within chromosome|
|3| Endpos| end position, if applicable|
|4| Ref| reference allele|
|5| Alt| alternate allele|
|6| esp6500siv2_all| alternate allele frequency based on all ethnicities provided in the NHLBI Exome Sequencing Project|
|7| ExAC_ALL| alternate allele frequency based on all ethnicities provided in ExAC?|
|8| 1000g2015aug_all| alternate allele frequency based on all ethnicities provided in 1000G, Aug 2015 (http://www.1000genomes.org/)|
|9| cg46| alternate allele frequency based on 46 unrelated samples sequenced and processed with the Complete Genomics pipeline|
|10| CADD| raw CADD score (deleterious-ness of the SNP/inDEL)|
|11| CADD_Phred| scaled score (1-99) * We limited this (due to data size and interest) to the top 10% of deleterious variants recieving a score. Thus, the max score listed will be 10. |
|12| Polyphen2_HDIV_score| the score that Polyphen2 gives the snp based on the HumDiv database.  usually NA in this file|
|13| Polyphen2_HDIV_pred| B/D/P (benign/damaging/possibly damaging)|
|14| Polyphen2_HVAR_score| the score that polyphen2 gives the snp based on the HumVar database.  usually NA in this file|
|15| Polyphen2_HVAR_pred| B/D/P (benign/damaging/possibly damaging)|
|16| consequence| Predicted variant functional consequence as determined by Variant Effect Predictor (VEP) (i.e. synonymous_variant,stop_gained,stop_lost,frameshift_variant,splice_acceptor_variant,splice_donor_variant)|
|17| gene_symbol| code for gene|
|18| family| family id number|
|19| fam_n_children| Total number of children in the family (from ped file)|
|20| fam_n_aff| Total number of affected children in the family (from ped file)|
|21| fam_n_unaff| Total number of unaffected children in the family (from ped file)|
|22| n_missing_aff| Total number of unaffected children in the family (from ped file)|
|23| n_missing_unaff| Number of unaffected children with an inheritance_type=missing|
|24| n_uncertain_aff| Number of affected children with an inheritance_type=uncertain|
|25| n_uncertain_unaff| Number of unaffected children with an inheritance_type=uncertain|
|26| *inheritance_type| Lists one or more inheritance types|
|27| n_aff_carriers| Number of affected children with an inheritance_type!=uncertain, missing|
|28| n_aff_noncarriers| Number of unaffected children that are homozygous reference at this site (not in the VCF or inheritance patterns file)|
|29| n_unaff_carriers| Number of unaffected children with an inheritance_type!=uncertain, missing|
|30| n_unaff_noncarriers| Number of unaffected children that are homozygous reference at this site (not in the VCF or inheritance patterns file)| fam_unaff_children - n_unaff_carriers  - n_missing_unaff - n_uncertain_unaff
|31| frac_of_aff| Fraction of the affected children carrying the varaint| n_aff_carriers/fam_n_aff
|32| frac_of_unaff| Fraction of the unaffected children carrying the varaint| n_unaff_carriers/fam_n_unaff
|33| frac_of_aff_missing_adjusted| Fraction of the affected children carrying the varaint and not missing| n_aff_carriers/(fam_n_aff-n_missing_aff)
|34| frac_of_unaff_missing_adjusted| Fraction of the unaffected children carrying the varaint and not missing| n_unaff_carriers/(fam_n_unaff-n_missing_unaff)
|35| frac_of_aff_uncertain_adjusted| Fraction of the affected children carrying the varaint and not uncertain| n_aff_carriers/(fam_n_aff-n_uncertain_aff)
|36| frac_of_unaff_uncertain_adjusted| Fraction of the unaffected children carrying the varaint and not uncertain| n_unaff_carriers/(fam_n_unaff-n_uncertain_unaff)
|37| frac_of_aff_missing_uncertain_adjusted| Fraction of the affected children carrying the varaint and not missing or uncertain| n_aff_carriers/(fam_n_aff-n_missing_aff-n_uncertain_aff)
|38| frac_of_unaff_missing_uncertain_adjusted| Fraction of the unaffected children carrying the varaint and not missing or uncertain| n_unaff_carriers/(fam_unaff_children - n_uncertain_unaff - n_missing_unaff)
|39| Info| LOTS of information here which we chose to annotate. It provides the source information for many of the other separated columns (e.g., consequence, Polyphen, 1000g).|

***Note:** In the family aggregation file, inheritance_type will be a comma separated list of all observed inheritance types for this variant in all children in this family (e.g., inherited_mother, newly_hemizygous), however, children with "uncertain" or "missing" variants will not be listed. If only "." is listed then all children were either "uncertain" and/or "missing". 
