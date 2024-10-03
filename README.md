# Week4-5

## Problem 1
### Amino Acid Sequence Count
Create a python code to count 
```bash
nano amino_count.py
```
Run in the terminal 

```bash
python amino_count.py

OUTPUT

Number of amino acids: 30
Number of bases in the open reading frame: 93
```

--- 
## Problem 2
### Run prodigal on one of the genomes you have previously downloaded (ecoli.fna)

Copy the ecoli file from root terminal
```bash
cp ../ecoli.fna .
```

```bash
module load prodigal
prodigal -i ecoli.fna -o ecoli.gbk -d ecoli_genes.fna
grep ">" ecoli_genes.fna -c > gene_count.txt
````

**OUTPUT: 4161**



--- 
## Problem 3
### Run prodigal on all of the genomes creating a .sh script and find which genome has the highest number of genes



```bash
touch Prodigal_Problem3.sh
nano Prodigal_Problem3.sh
```
Make executable and run it 
```bash
chmod +x Prodigal_Problem3.sh
sbatch Prodigal_Problem3.sh
```
**OUTPUT: prodigal_results.txt**



--- 
## Problem 4
### Annotate all genomes using prokka instead of prodigal.

Load the module 

```bash
module load prokka
```
Create **.sh** and code

```bash
touch Prokka_Problem4.sh
nano Prokka_Problem4.sh
```

Make executable and run it 
```bash
chmod +x prokka_Problem4.sh
sbatch prokka_Problem4.sh
```

**OUTPUT: cds_counts.txt**



## Problem 5
### Extract and list all unique gene names annotated by Prokka using shell commands

Shell commands 
```bash
grep -h "gene=" /home/alboeis/WEEK45/prokka_output/*/*.gff | sed 's/.*gene=//; s/;.*//' | sort -u > unique_gene_names.txt
head -n 5 unique_gene_names.txt
```

**OUTPUT:**  
First five gene names from the list **unique_gene_names.txt**

```
aaaT  
aaeA  
aaeA_1  
aaeA_2  
aaeB
```

# Save on git repository 
git push -u origin main 

