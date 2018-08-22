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
