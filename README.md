```
*******************************************************************
*   ____  ____ __     __  ____    _____  _     ____  _____   _    *
*  / ___|/ ___|\ \   / / |___ \  |  ___|/ \   / ___||_   _| / \   *
* | |    \___ \ \ \ / /    __) | | |_  / _ \  \___ \  | |  / _ \  *
* | |___  ___) | \ V /    / __/  |  _|/ ___ \  ___) | | | / ___ \ *
*  \____||____/   \_/    |_____| |_| /_/   \_\|____/  |_|/_/   \_\*
*                                                                 *
*   ____  ___   _   _ __     __ _____  ____  _____  _____  ____   *
*  / ___|/ _ \ | \ | |\ \   / /| ____||  _ \|_   _|| ____||  _ \  *
* | |   | | | ||  \| | \ \ / / |  _|  | |_) | | |  |  _|  | |_) | *
* | |___| |_| || |\  |  \ V /  | |___ |  _ <  | |  | |___ |  _ <  *
*  \____|\___/ |_| \_|   \_/   |_____||_| \_\ |_|  |_____||_| \_\ *
*                                                                 *
*******************************************************************
```

## CSV to FASTA CONVERTER

While CSV is ubiquitous throught the technology world, the file format may not be the best to share sequences among scientists.
This script converts a CSV file to FASTA file format capable of being read by popular bioinformatics programs.
An optional input allows the FASTA file to break the sequence into 100 nt chunks.

## Requirements
### Required dependecies 
Dependencies for script:
```
python 3.2 or above
```
The rest are standard Python libraries.

### Running the script
```
python csv2fasta.py Sequences.csv [-w]
```
The input file and script have to be in the same directory. The optional "-w" is written without brackets.

### Example
#### Input CSV file should have "Name" and "Sequence" headers

| Name      | Sequence            |
| :---      | :---                |
|DNA1       |  ATCGATCG           |
|DNA2       |  GATGC....AAGAAT    |

Note: DNA2 is more than 100 nt long.

#### Output 'Sequences.fasta' file WITHOUT the "-w" option

\>DNA1<br>ATCGATCG<br>
\>DNA2<br>GATGCATACTTCGT...ACAAAGAAT

#### Output 'Sequences.fasta' file WITH the "-w" option

\>DNA1<br>ATCGATCG<br>
\>DNA2<br>GATGCATACTTCGT...<br>ACAAAGAAT

### Notes and Limitations
#### Input file
- A .csv file. 
  - The extension must end with ".csv" or ".CSV".
  - Other extensions, including ".txt" files will not work.
  - Non UTF-8 characters may produce an error.
  - CSV files without header may skip the first Name:Sequence row. So check file after completion.
#### Output file 
  - File will be named "Sequences.fasta".
     - If wrapping is enabled, it will produce 100 nt lines until end of sequence.

Please let me know if you encounter any bugs or problems.

