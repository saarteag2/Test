## Practice Example

This repository contains sample data provided to practice creating a transmission summary with. The sample data consists of one inheritance patterns file for SNV/Indel variants, one inheritance patterns file for SV variants, and one ped file that can be used for with both of these files. 

**Running Transmission Summary for SNV/Indel Variants** <br>
Usage:
```
python make_transmission_flat_db.py <input_file INPUT_FILE > <--out_dir OUT_DIR> <prefix Prefix> <suffix Suffix> [--alt_ped_file ALT_PED_FILE]
```

Command:
```
python make_transmission_flat_db.py Practice_InheritancePatterns_SNVOrIndel.txt <--out_dir OUT_DIR> Sample_Data chr22 --alt_ped_file Practice.ped
```

**Running Transmission Summary for SV Variants** <br>
Usage:
```
python make_transmission_flat_db.py <input_file INPUT_FILE > <--out_dir OUT_DIR> <prefix Prefix> <suffix Suffix> --SV
```
Command:
```
python make_transmission_flat_db.py Practice_InheritancePatterns_SV.txt <--out_dir OUT_DIR> Sample_Data chrXY --alt_ped_file Practice.ped --SV
```
