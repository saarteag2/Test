## Coverage Plots README

The Coverage_Plots_UserInput_2018-08-16.R script parses the collated coverage metrics file and relationship file to create eight (8) plots.

1. Percent of targeted bases covered at >=X (1,10,20,30,40; box plot) <br>

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

#### Example Coverage Plots are available below ####
1. Percent of targeted bases covered at >=X (1,10,20,30,40; box plot) <br>
![Percentage of Targeted Bases Box Plot](https://preview.ibb.co/nd1V79/Percentage_Of_Target_Bases_Box_Plot.png)

2. Average fold coverage of targeted bases per sample by family relationship (box plot) <br>
![Average Fold Coverage](https://preview.ibb.co/eWjmVU/Average_Fold_Coverage.png)

3. Histogram of average coverage <br>
![Histogram of Average Coverage](https://preview.ibb.co/bL6iAU/Average_Coverage_Histogram.png)

4-8. Histogram of percent of target region covered at >=X (1,10,20,30,40)
![Histogram of Percentage Targeted Region >=1](https://preview.ibb.co/e5BuH9/Percentage_Targeted_Region1.png)
![Histogram of Percentage Targeted Region >=10](https://preview.ibb.co/hW2C4p/Percentage_Targeted_Region10.png)
![Histogram of Percentage Targeted Region >=20](https://preview.ibb.co/co0qPp/Percentage_Targeted_Region20.png)
![Histogram of Percentage Targeted Region >=30](https://preview.ibb.co/gF90Pp/Percentage_Targeted_Region30.png)
![Histogram of Percentage Targeted Region >=40](https://preview.ibb.co/miraqU/Percentage_Targeted_Region40.png)
