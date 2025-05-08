## Single Cell analysis

Citation: Zhang, S., Fang, W., Zhou, S. et al. Single cell transcriptomic analyses implicate an immunosuppressive tumor microenvironment in pancreatic cancer liver metastasis. Nat Commun 14, 5123 (2023). https://doi.org/10.1038/s41467-023-40727-7

# Processed sc-RNA seq data
Geo Accession number: GSE197177 

## Data extraction:
Sample codes:
ZC: normal pancreatic tissue
YF: pancreatic tumors
ZY: hepatic metastases
There are total 8 samples:        
GSM5910784	Case1-YF
GSM5910785	Case1-ZY
GSM5910786	Case2-ZC
GSM5910787	Case2-YF
GSM5910788	Case2-ZY
GSM5910789	Case3-YF
GSM5910790	Case3-ZY
GSM5910791	Case4-ZY

Processed single-cell RNA sequencing (scRNA-seq) data is available. A compressed folder was downloaded containing folders for matrix, features, and barcodes in TSV format. The barcodes folder contained individual files named after their respective barcodes.

I created new directories for each sample (totaling 8 directories), with each directory containing the matrix.tsv, features.tsv, and barcode.tsv files. Since the barcodes folder had individual files, I used a Python script to combine all the individual barcode files for each sample into a single file.

Python script:
import os
# Set the path to the folder containing your barcode files
barcode_folder = "path/to/the/folder"

# List all files in the folder (these are the barcodes without file extensions)
barcode_files = [f.split('.')[0] for f in os.listdir(barcode_folder) if os.path.isfile(os.path.join(barcode_folder, f))]

# Write the barcodes to barcodes.tsv
with open('barcodes.tsv', 'w') as f:
    for barcode in barcode_files:
        f.write(barcode + '\n')









