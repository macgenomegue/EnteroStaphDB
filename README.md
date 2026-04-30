Staphylococcus Enterotoxins (SEs) Database - EnteroStaphDB
Enterotoxigenic Staphylococcus Database

Overview
This repository contains a curated multi-FASTA database of Staphylococcus aureus enterotoxin (SE) and enterotoxin-like gene sequences, including known variants.

Staphylococcal enterotoxins are key virulence determinants responsible for staphylococcal food poisoning. Unlike infection-driven diseases, pathology is caused by ingestion of preformed toxins. Therefore, genomic detection of enterotoxin genes is essential for assessing toxigenic potential in foodborne isolates.

Contents
- Staphylococcus_SEs.fasta: curated nucleotide sequences of enterotoxin genes and variants (e.g. entA, entB, entC variants, entD, entH and others)

Sequences are formatted in multi-FASTA format with annotated headers, including protein identifiers, gene names, and functional descriptions.

Intended Use

This database is designed for:

- Whole genome sequencing (WGS) analysis
- Screening using BLAST+ or ABRicate
- Detection of classical and non-classical staphylococcal enterotoxin genes
- Identification of gene variants relevant for virulence profiling and food safety risk assessment

Recommended Tools

- BLAST+ (blastn)
- ABRicate

Recommended Parameters

- Minimum identity: 80%
- Minimum coverage: 95%

These thresholds allow detection of both conserved enterotoxins and sequence-divergent variants while limiting false positives.

Example Usage

BLAST+
makeblastdb -in Staphylococcus_SEs.fasta -dbtype nucl -out SE_db

blastn -query genome.fasta
-db SE_db
-out results.txt
-outfmt “6 qseqid sseqid pident length qcovs evalue bitscore”
-perc_identity 80

Filter results for coverage >=95%.

ABRicate
abricate –db Staphylococcus_SEs genome.fasta > report.tab

Ensure the database is installed in the ABRicate database directory.

Interpretation

Detection of enterotoxin genes indicates the genetic potential of a strain to produce staphylococcal enterotoxins.

Detection does not confirm toxin expression, protein production, or presence of toxin in the food matrix. Toxin production depends on environmental conditions, including temperature, pH, water activity, and growth phase.

Results must be interpreted alongside microbiological data (e.g. bacterial counts) and, where required, confirmatory toxin detection assays.

Limitations

- Database is limited to currently curated enterotoxin genes and known variants
- Novel or highly divergent toxin genes may not be detected
- Sequence similarity does not guarantee identical toxin activity
- Gene presence does not equate to toxin production or food safety risk without supporting evidence

Curation
Sequences were compiled from public databases and peer-reviewed literature, focusing on well-characterised staphylococcal enterotoxins and their variants. Inclusion criteria prioritise validated gene annotations and functional relevance.

Versioning

Version: 1.0
Date: 2026-04-30

Citation
If you use this database, cite both the associated publication and this repository.

Publication:
Macori G et al. Genome-wide profiling of enterotoxigenic Staphylococcus aureus strains used for the production of naturally contaminated cheeses. Genes. 2019;11(1):33.

Database:
Staphylococcus Enterotoxins Database. GitHub repository. Available at: https://github.com/macgenomegue/[REPOSITORY_NAME]

Suggested citation format:
Staphylococcus Enterotoxins Database (version 1.0). Available at: https://github.com/macgenomegue/[REPOSITORY_NAME]

Contact
Maintainer: Guerrino Macori
Institution: University College Dublin

License
This database is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).
Full licence text: https://creativecommons.org/licenses/by/4.0/
