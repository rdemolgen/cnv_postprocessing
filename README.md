## Python scripts for post-processing of SavvyCNV calls

1. `mask_regions.py`: More generic functions for data processing and reformatting
    i. `maskCnvRegions`: Mask unwanted regions (e.g. acens), decoy chromosomes
    ii. `cnvsToWorksheet`: Create an Excel worksheet containing CNV calls
2. `consolidate_cnvs.py`: Collection of functions designed to consolidate individual CNV calls in different ways
    i. `reciprocalJointCalling`: An alternative to SavvyCNV jointCalling. Finds reciprocally overlapping CNVs between family members.
    ii. `intersectSv0Calls`: Intersect CNVs that have been called per-chromosome and whole-genome in order to mitigate for chromosome-specific SV errors
    iii. `annotateReciprocalCnvs`: Find and annotate reciprocally overlapping 'large' (50kb bins) and 'small' (200bp bins) CNVs
3. `convert_joint_to_vcf`: This module takes in a tab-delimited file containing joint called CNVs and outputs a VCF file that conforms to VCF v4.2 standards
    i. `convertJointToDataframe`: Converts joint called CNVs into a dataframe format
    ii. `dataframeToVcf`: Convert dataframe to VCF format
    iii. `reformatVcf`: Ensure VCF conforms to v4.2 standards
4. `refomat_annotated_txt`: Reformat VEP-annotated CNVs into Trio-compatible format