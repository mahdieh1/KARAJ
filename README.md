


<p align="center">
  <img src="https://github.com/mahdieh1/KARAJ/blob/main/docs/karaj.jpg" />
</p>

========================================================================================================================================================================================

## A command-line software to streamline acquiring biological data

We here developed KARAJ a fast and flexible Linux command-line software to automate the end-to-end process of querying and downloading a wide range of file formats containing biological data. KARAJ automates four main tasks; firstly, it gives a summary list of accessible datasets generated by or used in a list of scientific articles and enables users to select whichever ones willing to download; secondly, KARAJ calculates the size of files users are willing to download and checks with the local driver to ensure the availability of adequate space in the local disk; thirdly, KARAJ generates the metadata table containing sample information and experimental design of the corresponding study; and lastly, it enables users to download supplementary data tables attached to publications. The KARAJ software is publicly available on https://rdrr.io/github/mahdieh1/XXX.


--------------------------------------------------------------------------------------------------------------------------------------------

## Table of Contents

- [Installation](#installation)
- [Required arguments](#required-arguments)
- [Common Error messages](#common-error-messages)
- [Examples](#examples)
- [How to use](#how-to-use)
- [Reference](#reference)
- [Author Info](#author-info)
- [Acknowledgements](#acknowledgements)
- [License](#license)

------------------------------------------------------------------------------------------------------------------------

## Installation

KARAJ runs on LINUX. Install the package from Github using the following commands.

```
cd /KARAJ
git clone https://github.com/Knowledge-Wisdom-Understanding/Auto-Recon.git
cd Auto-Recon
chmod +x setup.sh
./setup.sh
```
------------------------------------------------------------------------------------------------------------------------

### Required arguments

| Flags | Description | Default | Syntax | 
| :--- | :--- | :--- | :--- |  
| -l | The list of URL(s) | empty | `KARAJ -l [URL1 URL2 URL3 ... URLn ]` 
| -p	| The list of PMCID(s) | empty | `KARAJ -p [PMCID1 PMCID2 PMCID3 ... PMCIDn]`
| -o	| The output working directory | The current working directory | `KARAJ -o [working directory]`
| -t	| Type of files that user needs | KARAJ downloads all of file types | `KARAJ -t [bam/vcf/fastq ]`
| -s	| Specify the Suplemenatry data is necessary to download or not  | 0 | `KARAJ -l [1/0]`
| -f	| Specefiy file containing the URL(s) or PMCID(s) or Seqlist(s) in the working direcory: For downloading: (1) URL(s): please use Links for the filename and 1 as the flag value with the file name (PMlist =1) or (Links = 2) or (seqlist = 3)  (2) PMCID(s): please use Links for the filename and 0 as the flag value with the file name (PMlist =1) and (Links = 0) (3) seqlist(s): please use Links for the filename and 0 as the flag value with the file name (PMlist =1) and (Links = 0)  | KARAJ downloads based on the -l, -p or -i flags | `KARAJ -f [1/0]`   | KARAJ downloads based on the -l, -p or -i flags | `KARAJ -f [1/2/3]`
| -i	| The accession IDs that user needs| KARAJ downloads all of accession IDs | `KARAJ -i [SRR/SRP/PRJ/PRJNA]`
| -d	| Specefiy KARAJ downloads all files or selected files: (1): downloads the selected files, (0): downloads all files | KARAJ downloads all of files associated to the -l, -p, -f or -i flags| `KARAJ -d [1/0]`
| -m	| Specefiy KARAJ downloads metadata or not | empty | `KARAJ -m [URL(s)]?`
| -h	| Help | empty | `KARAJ -h `
| -u	| The list of PMCID(s) | empty | `KARAJ -l [URL(s)]`
| -c	| The number of threads| (the number of cores accessible in the system -1) | `KARAJ -c [core]`

------------------------------------------------------------------------------------------------------------------------
## Common Error messages

| Error message | Description |
| :--- | :--- | 
| Invalid option, please see the Help using -h option | The error message states that you cannot use the KARAJ command with the determined flags. |
|Argument missing from ID option|The error message states that you miss value after the argument ID.|
|You missed one of the obligatory arguments|The error message states that all of the flags ( -p, -l, -f, -i) are empty. You need to run KARAJ command with one of these obligatory flags.|
|You enter two obligatory flags with each other. Please enter one of these flags.|The error message states that you enter arguments of (-p, -l, -f) with each other. Karaj fetch and download one types of file in each run. |
|No sample found. Either the provided ID is invalid or raw data was not provided for this record. | The error message states that raw data is not accessible with the one of IDs ( -p, -l, -f, -i) you enter. |
| Directory does not have enough space for all files you aim to download. Please change the directory. |The error message states that there is no space in the working directory to download data.|


------------------------------------------------------------------------------------------------------------------------
## Examples

```
1. Command for downloading BAM files:
$ ./KARAJ.sh -p PMC6197289 -t bam  

2. Command for downloading VCF files:
$ ./KARAJ.sh -l https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4750478/ -t vcf  

3. Command for downloading FASTQ files:
$ ./KARAJ.sh -i PRJNA521732 -t fastq


```
------------------------------------------------------------------------------------------------------------------------
## How to use

Before using KARAJ, you need to run make file with the following commands:

```
./makebash.sh

```

------------------------------------------------------------------------------------------------------------------------

## Reference
```
Please consider citing the follow paper when you use this code.
  Title={KARAJ: a command-line software to streamline acquiring biological data},
  Authors={Mahdieh Labani, Amin Beheshti, Nigel Lovell, Hamid Alinejad-Rokny, Ali Afrasiabi}
}
```
------------------------------------------------------------------------------------------------------------------------

## Contacts

I will be pleased to address any question or concern about the KARAJ package:
In case of queries, please email: m.labani@unsw.edu.au or a.afrasiabi@unsw.edu.au


------------------------------------------------------------------------------------------------------------------------

## Author Info
### People who contributed to the KARAJ idea and code:
* Mahdieh Labani 
* Ali Afrasiabi
* Amin Beheshti
* Hamid Alinejad-Rokny
* Nigel Lovell

------------------------------------------------------------------------------------------------------------------------

## Acknowledgements
This work was funded by the UNSW Scientia Program Fellowship and the Australian Research Council Discovery Early Career Researcher Award (DECRA), Macquarie PhD Scholarship and Australian Government Research Training Program (RTP) scholarship. Analyses were made possible with High Performance Computing resources provided by the BioMedical Machine Learning Lab with funding from the Australian Government and the UNSW SYDNEY.

------------------------------------------------------------------------------------------------------------------------

## License

This package is free software; you can redistribute it and/or modify it under the terms of the , MIT License as published by the Free Software Foundation.


