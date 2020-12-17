# Over half of men and 28% of women aged 65-70 died in Manaus, Brazil by July, 2020 (README)
Adam Zimmerman  
adam.eric.zimmerman@gmail.com  
December 10, 2020  

#### Overview

What happened in the Amazon and São Paulo during the COVID-19 pandemic? 

Click through to `Report.pdf` for an exploratory analysis of three epidemiological and one genetic data sets. They show that the city of Manaus, and its Northern Brazilian state, Amazonas, were hit harder per capita than the city and state of São Paulo through the second and third quarters (Q2; Q3) of 2020.

#### Methods

Throughout 2020, Oxford University hosted and made freely accessible a large amount of tabular epidemiological COVID-19 data from across the world [(OxCOVID19)](https://covid19.eng.ox.ac.uk/). This provided the demographics and case rates data of Manaus and São Paulo (Figures 1-3).

Prowse and colleagues reported on herd immunity in the Amazon and Northern Brazil, providing risk factor data, including mortality by age and sex (Figures 4-5; [Prowse _et al_., 2020](https://www.medrxiv.org/content/early/2020/10/15/2020.09.25.20201939)).

Across Q2 and Q3 of 2020, scientists across Norhtern Brazil and the Amazon collected 33 Illumina NGS samples and posted them as `.fasta` files on the website of the National Center for Biotechnology Information (NCBI) under the project number [PRJNA662684](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA662684).

Within a [Makefile](https://www.gnu.org/software/make/manual/make.html), quality checking scripts demonstrated the high quality of the majority of this data. Next, a trimmomatic script based on code by [Data Carpentry](https://datacarpentry.org/wrangling-genomics/03-trimming/index.html) removed the shorter, lower quality runs from the analysis. Several more bash scripts based on code by [C. Titus Brown and colleagues](https://angus.readthedocs.io/en/2017/variant-calling.html) compared the reads to the NCBI's reference SARS-CoV-2 genome to output a `.vcf` variant call format file for interpretation in RStudio. Lastly, single nucleotide polymorphisms (SNPs) were checked for quality (Figure 7) and grouped by position and nucleotide substitution (Figure 8).

#### Results

From Q2 into Q3, the intense period of infection correlated with the emergence of an antibody prevalence among Manaus blood donors that was approximately threefold greater than antibody prevalence among São Paulo blood donors (Figure 4; [Buss _et al_., 2020](https://www.medrxiv.org/content/early/2020/09/21/2020.09.16.20194787)). This was an indication of good news and herd immunity for Manaus, heading into Q4. But the path to that antibody prevalence was characterized by a two- to three-fold increase in mortality for Manaus residents, especially those that were male and over 65 (Figure 6; [Prowse _et al_., 2020](https://www.medrxiv.org/content/early/2020/10/15/2020.09.25.20201939)). Over half of Manaus men aged 65-70 died.

Genetic data contributed one more distinct, undeniable trend for the Amazon. A variant call analysis of 33 SARS-CoV-2 samples from patients across the Northern Brazilian states surrounding Manaus showed that the great majority of single nucleotide polymorphisms (SNPs) displayed transitions from thymine to cytosine (Figure 8).

#### Acknowledgements
All of the shell scripts were contributed by [Naupaka Zimmerman](https://github.com/naupaka). Parts of this pipeline approach are based on the pipeline described in the [Data Carpentry Genomics lessons](https://datacarpentry.org/genomics-workshop/), which are made available under a [CC-BY 4.0 license](https://creativecommons.org/licenses/by/4.0/). See `Report.pdf` for full Sources Cited.

