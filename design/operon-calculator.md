# Operon Calculator

## Summary

The Operon Calculator is a design algorithm for engineering bacterial operons with controllable protein expression levels. In Predict mode, the Operon Calculator predicts the translation rates for each protein coding sequence, calculates the mRNA transcript's stability, and identifies undesired genetic elements that exist inside the operon sequence, including internal promoters, internal transcriptional terminators, ribosomal pause sites, highly translated internal start codons, repetitive DNA sequences, transposon insertion sites, and phage insertion sites. In Design mode, the Operon Calculator generates an optimized bacterial operon sequence with designed ribosome binding sites and protein coding sequences that maximally satisfy several user-defined objectives. Selectable objectives include:

1. Targeted translation initiation rates for each protein coding sequence
2. Organism-specific synonymous codon optimization for each protein coding sequence
3. Higher mRNA stabilities
4. Fewer internal promoters
5. Fewer internal transcriptional terminators
6. Fewer internal start codons with high translation initiation rates
7. Fewer repetitive DNA sequences above 12 bp long
8. Fewer ribosomal pause sites
9. Fewer transposon insertion sites and phage insertion sites (genetic instability sites)
10. Reduce DNA synthesis complexity (e.g. homopolymers and regions with extreme GC%).&#x20;

Additional design constraints can be used to customize the operon design. Non-repetitive promoters and transcriptional terminators may be inserted at the beginning and end of the operon. Restriction sites can be inserted at desired locations and excluded from all other locations.

#### Web Interface Links

[Operon Calculator Predict Mode](https://www.denovodna.com/software/predict\_operon\_calculator)

[Operon Calculator Design Mode](https://www.denovodna.com/software/design\_operon\_calculator)

## Operon Calculator Predict Mode

### **Inputs**

**Title:** the name of your design job \[optional]

**Host Organism:** the bacterial species used to express the operon, selectable from a long list (start typing to narrow down your choices).

**Promoter Name:** the name of the selected promoter \[optional, auto-completed when a promoter is selected from our genetic parts database]

**Promoter Sequence:** the nucleotide sequence of the promoter used to transcribe the operon \[auto-completed when a promoter is selected from our genetic parts database]

**Number of Protein CDSs:** the number of protein coding sequences in the operon (1 to 10).

**RBS Sequence:** for each CDS in the operon, the nucleotide sequence of its ribosome binding site. (ATCGU nucleotides allowed).

**Protein Coding Sequence:** for each CDS in the operon, the nucleotide sequence of the protein coding sequence, starting from the start codon and ending at the stop codon. ATCGU nucleotides allowed.

**Transcriptional Terminator Name:** the name of the selected transcriptional terminator \[optional, auto-completed when a terminator is selected from our genetic parts database]

**Transcriptional Terminator Sequence:** the nucleotide sequence of the transcriptional terminator at the end of the operon \[auto-completed when a terminator is selected from our genetic parts database]

### Advanced Options

**Translation Rate Model Version:** the free energy model used to carry out translation initiation rate predictions. New versions are developed as more interactions are quantitatively characterized and incorporated into the model. \[optional]

### Outputs

**Translation Initiation Rates:** the predicted translation initiation rates for each protein coding sequence on a proportional scale from 1 to 100,000+.&#x20;

**Translation Elongation Rates:** the averaged synthesis rate for each protein coding sequences in units of nucleotides per second.&#x20;

**Undesired Genetic Elements:** identified internal start codons, internal promoters, internal terminators, transposon insertion sites, and phage insertion sites.&#x20;

**Translated Open Reading Frames:** a plot showing the translation initiation rates for each protein coding sequence in the mRNA transcript at their respective locations. mRNA transcripts often contain multiple start codons, yielding multiple (potentially overlapping) open reading frames. The open reading frames with the highest translation initiation rates are favored by the ribosome for synthesis of the corresponding proteins.

**mRNA Stability Calculations:** the predicted decay rate of the operon's mRNA transcript, including all its protein coding sequences. The calculations consider the sequence and structure of the 5' untranslated regions as well as the translation rates of each protein coding sequence. The contributions to the prediction include RNase binding probabilities and the level of ribosome protection (quantified by the average unprotected distance between ribosomes).&#x20;

**Ribosome Binding Free Energy Calculations:** a detailed table showing the free energy calculations used to predict the RBSs' translation initiation rates. Each Gibbs free energy change is the quantification of an interaction between the ribosome and mRNA that affects its translation initiation rate. [Read more about the RBS Calculator's free energy model](rbs-calculator/rbs-calculator-free-energy-model.md).&#x20;

**Operon Sequence:** the operon sequence. Click "Download Genbank" to download the operon sequence in Genbank format with several annotations.

## Operon Calculator Design Mode

### **Inputs**

**Title:** the name of your design job \[optional]

**Host Organism:** the bacterial species used to express the operon, selectable from a long list (start typing to narrow down your choices).

**Promoter Name:** the name of the selected promoter \[optional, auto-completed when a promoter is selected from our genetic parts database]

**Promoter Sequence:** the nucleotide sequence of the promoter used to transcribe the operon \[auto-completed when a promoter is selected from our genetic parts database]

**Number of Protein CDSs:** the number of protein coding sequences in the operon (1 to 10).

**Target Translation Initiation Rate:** for each CDS in the operon, a desired translation initiation rate on a proportional scale from 1 to 100,000+. The maximum possible translation initiation rate is over 5,000,000; however, depending on the protein coding sequence, the maximum rate is not always achievable.&#x20;

**Protein Coding Sequence:** for each CDS in the operon, the protein coding sequence, starting from the start codon and ending at the stop codon. Either amino acids ([IUPAC 1-letter code](iupac-codes.md#iupac-amino-acid-code)) or ATCGU nucleotides allowed.

**Transcriptional Terminator Name:** the name of the selected transcriptional terminator \[optional, auto-completed when a terminator is selected from our genetic parts database]

**Transcriptional Terminator Sequence:** the nucleotide sequence of the transcriptional terminator at the end of the operon \[auto-completed when a terminator is selected from our genetic parts database]

### Advanced Options

**Selectable Design Rules:** Activate or de-activate individual rules to customize the design of the bacterial operon.&#x20;

**Exclude Restriction Enzyme Sites:** select restriction enzymes from an auto-complete list (start typing to narrow down choices). The restriction enzymes' recognition sequences will be excluded from the designed operons.&#x20;

**Synonymous Codon Tables:** select a type of synonymous codon table. Either 'Highly Translated Synonymous Codons' to maximize translation elongation rates for all CDSs or 'Balanced Synonymous Codons' to tailor translation elongation rates according to the translation initiation rate of each CDS. Select 'Highly Translated Synonymous Codons' when a small number of CDSs will be over-expressed or when an operon library might over-express several CDSs. Select 'Balanced Synonymous Codons' when many CDSs (possibly across many operons) will be expressed at varied levels (not all over-expressed).

**RBS Sequence Constraints:** for each CDS in the operon, a degenerate nucleotide sequence that controls which nucleotides are allowed to be chosen during RBS design. Degenerate nucleotides follow the [nucleotide IUPAC code](iupac-codes.md#iupac-nucleotide-code) (ATCGUSRMWKYVBDHN allowed). \[optional]

**Translation Rate Model Version:** the free energy model used to carry out translation initiation rate predictions. New versions are developed as more interactions are quantitatively characterized and incorporated into the model. \[optional]

### Outputs

**Multiple Operon Designs:** several designed operons with equally optimal characteristics. The characteristics of each designed operon are listed, including:

1. The translation initiation rates (TIR) of each protein coding sequence on a proportional scale from 1 to 100,000+.&#x20;
2. The translation elongation rates (TER) of each protein coding sequence (nucleotides per second).
3. The number of highly translated internal start codons (HTISC) within each protein coding sequence.
4. The length of the longest repeat across the operon (nucleotides).&#x20;
5. The number of internal promoters.
6. The number of internal transcriptional terminators.
7. The number of undesired restriction sites (excluded).
8. The number of undesired RNase binding sites.
9. The number of genetic instability sites (transposon insertion sites or phage insertion sites).

_**Click on an operon design to examine it further.**_&#x20;

**Translation Initiation Rates:** for the selected operon, the predicted translation initiation rates for each protein coding sequence on a proportional scale from 1 to 100,000+.&#x20;

**Translation Elongation Rates:** for the selected operon, the averaged synthesis rate for each protein coding sequences in units of nucleotides per second.&#x20;

**Undesired Genetic Elements:** for the selected operon, the identified internal start codons, internal promoters, internal terminators, transposon insertion sites, and phage insertion sites.&#x20;

**Translated Open Reading Frames:** for the selected operon, a plot showing the translation initiation rates for each protein coding sequence in the mRNA transcript at their respective locations. mRNA transcripts often contain multiple start codons, yielding multiple (potentially overlapping) open reading frames. The open reading frames with the highest translation initiation rates are favored by the ribosome for synthesis of the corresponding proteins.

**mRNA Stability Calculations:** for the selected operon, the predicted decay rate of the operon's mRNA transcript, including all its protein coding sequences. The calculations consider the sequence and structure of the 5' untranslated regions as well as the translation rates of each protein coding sequence. The contributions to the prediction include RNase binding probabilities and the level of ribosome protection (quantified by the average unprotected distance between ribosomes).&#x20;

**Repetitive DNA Sequences:** the longest repetitive sequence in the DNA fragment, the repeat distribution (the number of repetitive sequences with different lengths), and a repeat chord diagram illustrating the locations of the repetitive sequences. A full list of repeats is also shown, including their types, lengths, and sequences.&#x20;

**Ribosome Binding Free Energy Calculations:** for the selected operon, a detailed table showing the free energy calculations used to predict the RBSs' translation initiation rates. Each Gibbs free energy change is the quantification of an interaction between the ribosome and mRNA that affects its translation initiation rate. [Read more about the RBS Calculator's free energy model](rbs-calculator/rbs-calculator-free-energy-model.md).&#x20;

**Operon Sequence:** the sequence of the selected operon. Click "Download Genbank" to download the operon sequence in Genbank format with several annotations.

## Relevant Articles

[Cetnar, D. P., & Salis, H. M. (2020). Systematic Quantification of Sequence and Structural Determinants Controlling mRNA stability in Bacterial Operons. bioRxiv.](https://www.biorxiv.org/content/10.1101/2020.07.22.216051v1)

[Reis, A.C. & Salis, H.M. (2020). An automated model test system for systematic development and improvement of gene expression models. ACS Synthetic Biology, 9(11), 3145-3156.](https://doi.org/10.1021/acssynbio.0c00394)

[Halper, S. M., Hossain, A., & Salis, H. M. (2020). Synthesis Success Calculator: predicting the rapid synthesis of DNA fragments with machine learning. ACS Synthetic Biology, 9(7), 1563-1571.](https://doi.org/10.1021/acssynbio.9b00460)

[Farasat, I., Kushwaha, M., Collens, J., Easterbrook, M., Guido, M., & Salis, H. M. (2014). Efficient search, mapping, and optimization of multi‐protein genetic systems in diverse bacteria. Molecular systems biology, 10(6), 731.](https://doi.org/10.15252/msb.20134955)

[Ng, C. Y., Farasat, I., Maranas, C. D., & Salis, H. M. (2015). Rational design of a synthetic Entner–Doudoroff pathway for improved and controllable NADPH regeneration. Metabolic engineering, 29, 86-96.](https://doi.org/10.1016/j.ymben.2015.03.001)
