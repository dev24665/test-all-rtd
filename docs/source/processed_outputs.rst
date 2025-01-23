Processed outputs from PDC Common Data Analysis Pipeline
==============
What analytical quantitation workflows are used in PDC studies?
----------------
Most studies from CPTAC and other programs in PDC use an isobaric labelling protein quantitation workflow, in which multiple biological samples are labeled with an identifying reagent (the isobaric tag) and mixed before tandem mass-spectrometry analysis. The isobaric tag reagents are named based on the technique and their multiplexing capacity, iTRAQ reagents provide 4-plex analyses, while TMT-n provide n-plex analyses, for n = 10, 11, 16, and 18. Isobaric tags are quantified in each identified tandem mass-spectrum of a peptide, but since peptide intensities vary a lot, all isobaric tag intensities must be normalized with respect to one of the tags in each spectrum. The resulting ratios can be summarized by averaging the ratios for the peptides from a protein. To expand the number of biological samples in CPTAC studies beyond the capacity of the isobaric tag reagents, a common reference sample is included in all analytical samples and its tag’s intensities used as the ratio denominator throughout.

A small number of older CPTAC studies use a label-free quantitation workflow, without labelling reagents, and quantify peptides based on the integrated area under the elution profile of each precursor ion (precursor area) and the number of peptides identified from the protein (spectral counts).

The isobaric labelling quantitation workflows provide relative protein abundance, relative to the common reference sample, while the label-free quantitation workflows provide absolute protein abundance without reference to any other sample.

What summary report files provide protein abundance values?
----------------
For processed protein abundance, download the quantitation report file based on the quantitation workflow, and labeling reagent where appropriate, used in the study:

TMT Workflow: *.tmt10.tsv, *.tmt11.tsv, *.tmt16.tsv, *.tmt18.tsv
iTRAQ Workflow: *.itraq.tsv
Label-free Workflow: *.precursor_area.tsv or *.spectral_count.tsv
Each of these summary reports provide protein abundance values for the biological samples analyzed in the study. TMT and iTRAQ workflows provide relative protein abundance values, while the label-free workflow provides absolute protein abundance values.

What are the Summary Report files?
----------------
- Protein Identification Reports:

*.summary.tsv: Summary of the evidence for identified proteins. Generated through a conservative gene-based generalized parsimony analysis, which uses identified peptides to identify proteins.
*.peptides.tsv: Summary of the evidence for identified peptides.
- Protein Quantitation Reports:

*.precursor_area.tsv: Label-free workflow protein quantitation by precursor peak area integration.
*.spectral_count.tsv: Label-free workflow protein quantitation by spectral counts.
*.itraq.tsv: iTRAQ workflow protein relative quantitation.
*.tmt10.tsv: TMT-10 workflow protein relative quantitation.
*.tmt11.tsv: TMT-11 workflow protein relative quantitation.
*.tmt16.tsv: TMT-16 workflow protein relative quantitation.
*.tmt18.tsv: TMT-18 workflow protein relative quantitation.
- Site-specific PTM Reports:

*.phosphopeptide.tsv and *.phosphosite.tsv: Phosphopeptide relative quantitation reports.
*.glycopeptide.tsv and *.glycosite.tsv: Deglycosylated N-linked glycopeptide relative quantitation reports.
*.acetylpeptide.tsv and *.acetylsite.tsv: Acetylated peptide relative quantitation reports.
*.ubiquitylpeptide.tsv and *.ubiquitylsite.tsv: Cleaved ubiquitilated peptide relative quantitation reports.
Site-specific PTM reports are only available for the isobaric labelling quantitation workflows and represent the summary of spectral ratios across similarly modified peptides and modified protein sites.

Why are there different numbers of samples in the identification and quantitation files?
----------------
Identification files (e.g., *.summary.tsv) contain information about analytical samples, which are usually (TMT, iTRAQ workflows) a mixture of multiple biological samples. Quantitation files (e.g., *.tmt11.tsv, *.itraq.tsv) provide relative abundance values for each individual biological sample after de-multiplexing. Only the label-free quantitation workflow has a single biological sample in each analytical sample.

How many clinical biospecimens are quantitated in each analytical sample?
------------------
In the isobaric labelling quantitation workflows, one of the isobaric tags is assigned to the common reference sample. Usually, the same isobaric tag is used for the common reference sample in every analytical sample, generally it is the first or last tag. Consequently, for studies using labelling reagents with a plex capacity of n, n-1 labels will be used for clinical biospecimens.

Why do spectral counts appear in TMT and iTRAQ workflows?
-------------------
Spectral counts in the identification summary report (`*.summary.tsv`) are for analytical samples, which usually represent multiple biological samples, and provide evidence for identified proteins.

What do the 'Log ratio' and 'Unshared Log ratio' columns represent?
-------------------
In the isobaric labelling quantitation workflow files (e.g., `*.tmt11.tsv`):

Log Ratio: Includes relative quantitative values from all peptides that map to a specific protein.
Unshared Log Ratio: Excludes data from peptides shared between identified proteins, using only uniquely mapped peptides to compute the relative protein abundance.
While each protein must have its own peptide evidence for peptide identification, it is unclear whether the ratios observed for shared peptides should be added to each genes’ average ratio. These two versions of the ratio represent two extremes. While these two ways of summarizing the relative protein abundance usually produce quite similar values, the Unshared Log Ratio values may represent the summary of fewer values, while the Log Ratio values may represent the convolution of two different, homologous proteins’ relative quantitation values.

Where is the relative abundance of individual peptides? My proteins of interest share many peptide identifications.
--------------------
The Unshared Log Ratio relative protein quantitation values summarize only the ratios of peptides which are not shared between identified proteins, so this may be sufficient for your needs. If not, you can find the individual reporter ion intensities in the PSM and mzIdentML files, for each identified tandem mass-spectrum and aggregate these to peptides.

Why don’t you provide absolute abundance of proteins?
--------------------
The isobaric labelling quantitation workflow produces peaks for the isobaric tags in each tandem mass-spectrum, but the peak intensity of different peptides’ ions is not consistent with each other and their protein’s absolute abundance. However, the ratio of reporter ion peak intensities for different peptides is consistent across peptides, and the repeated observations can be used to estimate the relative abundance of a protein between samples.

How can I map internal sample IDs to case submitter IDs?
---------------------
Each analytical sample in the `*.sample.txt` file represents a mixture of biological samples. The file contains biospecimen_submitter_ids, which can be linked to case_submitter_ids using the Biospecimen tab on the PDC website.

Why don't the summary statistics (Mean, Median, StdDev) in the quantitation files match my calculations?
---------------------
The summary statistics in the quantitation files are computed before median normalization of the log2ratio values. To match these statistics, you need to add the median back to each column.
