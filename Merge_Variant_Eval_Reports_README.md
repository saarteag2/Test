## Merge VariantEval Reports README

The Merge_Variant_Eval_Reports.py script merges the CompOverlap, CountVariants, and TiTvVariantEvaluator modules in the VariantEval Report files per chromosome in a given directory. 

*Note: The script will ignore modules other than ones listed above.*

**Usage:**
```
python Merge_Variant_Eval_Reports.py --VariantEvalDir <Directory with Variant Eval Report files> --prefix <Prefix of Variant Eval Report files> --suffix <Suffix of Variant Eval Report files> --output_dir <Output directory>
```

**Rules for Merging Modules:** <br>

* **CompOverlap module/table:** <br>
        - compRate = (nVariantsAtComp/nEvalVariants)*100 <br>
        - concordantRate = (nConcordant/nVariantsAtComp)*100 <br>
        
*  **CountVariants module/table:** <br>
        - variantRate = nVariantLoci/nProcessedLoci <br>
        - variantRatePerBp = nProcessedLoci/nVariantLoci <br>
        - heterozygosity = nHets/nProcessedLoci <br>
        - heterozygosityPerBp = nProcessedLoci/nHets <br>
        - hetHomRatio = nHets/nHomVar <br>
        - indelRate = (nInsertions+nDeletions)/nProcessedLoci <br>
        - indelRatePerBp = nProcessedLoci/(nInsertions+nDeletions) <br>
        - insertionDeletionRatio = nInsertions/nDeletions <br>
        
* **TiTvVariantEvaluator:** <br>
        - tiTvRatio = nTi/nTv <br>
        - TiTvRatioStandard = 2.00 <br>
        - tiTvDerivedRatio = nTiDerived/nTvDerived <br>
