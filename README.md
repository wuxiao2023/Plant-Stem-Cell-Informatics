# Directory structure：

- Gene_number.txt: The file contains correspondence between numbers and genes.
- data: Data files on which jar package execution depends. The data file and jar package must be in the same directory.
- tools: Blast and hmmsearch tools for jar package execution dependencies.
    1. hmmer: The compilation package of hmmer downloaded on Mac.
    2. hmmer-linux: The compilation package of hmmer downloaded on linux.
    3. hmmer-windows: The compilation package of hmmer downloaded on windows.
    4. ncbi-blast-linux: The compilation package of blast downloaded on Mac.
    5. ncbi-blast-macosx: The compilation package of blast downloaded on linux.
    6. ncbi-blast-win: The compilation package of blast downloaded on windows.
- psci.jar: Main program, jar execution file

# Preparing the input file

The fasta file of protein sequences is required to run successfully.

# Execute instructions:

> java -jar psci.jar [options] -in <filename>

### Parameter Description:
``` 
# Plant-Stem-Cell-Informatics: Identify genes related to stem cells in plants
USAGE
  java -jar /Plant-Stem-Cell-Informatics/project/psci.jar [options] -in <filename>

OPTIONS
  -help: show brief help on version and usage
  -in <file>: input file name
  -gene <array>: corresponding number of the gene to be identified (Format: num1,num2) and the correspondence is in Gene_number.txt [Defult = all genes related to stem cells]
  -e1 <x>: report sequences <= this evalue threshold in output when running blast [Defult = 1e-5] (x > 0)
  -e2 <x>: report sequences <= this evalue threshold in output when running hmmsearch [Defult = 1e0] (x > 0)
  -o <dir>: output to directory <dir>
  -log 1: keep result files generated by running blast (outfmt = 0 and 6) and hmmsearch

We default to output the first 1000000 sequences that conform to evalue when running blast
```

# Result files

Result.txt: The resulting genes were identified and the corresponding information (tab separated).
Protein_sequences.txt: The id and corresponding protein sequences of resulting genes.

When the execution is successful, the directory where txt is located will be output: Result path: ./OutFolder

# Note:
The folders in the Tools tool directory can be used to delete unnecessary toolkits according to different system environments.
