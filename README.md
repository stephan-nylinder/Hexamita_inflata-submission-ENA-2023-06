# Hexamita_inflata-submission-ENA-2023-06
Submission of odd intron free de novo genome assembly with raw data to ENA

This is a description of the submission process of a de novo assembly genome to ENA on the species Hexamita inflata. The reason for the documentation is due to the genome being virtually intron free, or containing very short intron segments (< 10 bp).

Data belongs to Redmine #6700 (initiated 2023-03-14).

## DNA seq
- Illumina MiSeq
- PacBio RSII
- Oxford Nanopore

## RNA seq
- Illumina MiSeq

## Assembly
- .gff
- Assembly .fastq

Contact information for the project was a PhD who was only involved in the analysis part. Other information was obtained by proxy of the PhD from other project participants. This is a common setup and not very smooth in terms of information transfer between people involved.

# Initial contact and orientation (2023-03-15 - 2023-03-17)
First contact with PhD was made in 2023-03-15 by mail to arrange meeting to sort out details on the submission process. DS and PhD agreed for DS to be broker using the PhD ENA credibilities. Project lacked Uppmax resources and data was agreed to be transferred to the DS to facilitate the submission (non-sensitive).

# Data Transfer (2023-03-19 - 2023-04-03)
Data transfer was semi-complicated due to this being a non-Uppmax project. Solution was to use Uppsala Box for file transfer from PhD to DS. Issues on the PI-side delayed the transfer with ~1 week.

# Sample registration
Since this was a de novo genome assembly there was only one tissue type sampled. Registration of a single sample therefore appeared as plausible. Sample was registererd after completion of metadata using a generic template of ENA by the PhD. Suggested registration of the sample by the PhD was unsuccessful, the reason being the presense of row 1 making the validation fail. After deleting row 1, and spell checking the contents of the .tsv values, the sample registration was successful.

# Validation of data
Prior to validation the manifest foreach data type were assembled as simple .txt files. Missing information on insert sizes and short data description was provided by the PhD. DNA reads were validated using webin-cli with -validate flag, and passed for all DNA reads. Similar validations for RNA-Seq data first failes due to the incorrect files being sent, and then more errors with the correct files due to duplicate read names in the fastq-files:

```
ERROR: Multiple (6) occurrences of read name "M03094:10:000000000-AM3MD:1:2102:4704:15155/1" at: 
[.../raw/RNA_seq/RNA-1_unique.fastq.gz, read 522,
.../raw/RNA_seq/RNA-1_unique.fastq.gz, read 523,
.../raw/RNA_seq/RNA-1_unique.fastq.gz, read 775,
.../raw/RNA_seq/RNA-1_unique.fastq.gz, read 776,
.../raw/RNA_seq/RNA-1_unique.fastq.gz, read 803,
.../raw/RNA_seq/RNA-1_unique.fastq.gz, read 804]
```

The error can potentially stem from bad data, or file corruption during download. Access to original files are required for proper checks, and therefore the issue was sent back to the PI to sort out before submission of the data will be possible.

### Registration of locus tag


