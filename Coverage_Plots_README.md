## Coverage Plots README

The Coverage_Plots_UserInput_2018-08-16.R script parses the collated coverage metrics file and relationship file to create eight (8) plots.

1. Percent of targeted exonic bases covered at >=X (1,10,20,30,40; box plot) <br>

2. Average fold coverage of targeted bases per sample by family relationship (box plot) <br>

3. Histogram of average coverage <br>

4-8. Histogram of percent of target region covered at >=X (1,10,20,30,40)

#### Usage: ####
```
Rscript Coverage_Plots_UserInput_2018-08-16.R <Input File> <Region> <Project> <Relationship file> <Output Dir>
```
* **Input File**: Absolute path to cohort aggregate coverage file <br>
  * The cohort aggregate coverage file is a tab delimited file with a header in the format 

    | SampleID| CovType| AvgCvg| ge1x| ge10x| ge20x| ge30x| ge40x|
    | --- | --- | --- | --- | --- | --- |  --- | --- |
    | *'SampleID'*| *'CovTyp'*| *'AvgCvg'*| *'ge1x'*| *'ge10x'*| *'ge20x'*| *'ge30x'*| *'ge40x'*|

    * Note: In the case of Neuroregulome this file should be in the format

      | SampleID| Core_Wrong_ID| CovType| AvgCvg| ge1x| ge10x| ge20x| ge30x| ge40x|
      | --- | --- | --- | --- | --- | --- |  --- | --- | --- |
      | *'SampleID'*| *'Core_Wrong_ID'*| *'CovTyp"*| *'AvgCvg'*| *'ge1x'*| *'ge10x'*| *'ge20x'*| *'ge30x'*| *'ge40x'*|
    
* **Region**: Specific region that will be plotted ("Genomic", "Exonic", or "Target")
* **Project**: Specific project name to be used in plot titles (eg., Neuroregulome, iHART, etc.)
* **Relationship file**: Absolute path to relationship file
        * The relationship file is a tab delimited file with a header in the format [SampleID\tRelationship]. 
          Each SampleID is labled with one of the following relastionships: Father, Mother, Proband, Sibling
* **Output Dir**: Absolute path to output directory for coverage plots

#### Example of Coverage Plots are available below ####
1. Percent of targeted exonic bases covered at >=X (1,10,20,30,40; box plot) <br>
![Box Plot](https://image.ibb.co/fJ1xn9/Screen_Shot_2018_09_14_at_11_40_09_AM.png)
2. Average fold coverage of targeted bases per sample by family relationship (box plot) 


3. Histogram of average coverage 

4-8. Histogram of percent of target region covered at >=X (1,10,20,30,40)
