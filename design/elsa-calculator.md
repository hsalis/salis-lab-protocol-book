# ELSA Calculator

## Summary

The Extra Long sgRNA Array (ELSA) Calculator is a design algorithm that generates highly non-repetitive arrays for expression of many single-guide RNAs for use in multiplexed CRISPR applications.  The ELSA Calculator combines a biophysical model of CRISPR activity with toolboxes of non-repetitive promoters, sgRNA handles (Cas9), transcriptional terminators, and neutral DNA spacers to design the many-sgRNA arrays. If target sequence regions are provided, the ELSA Calculator will automatically design guide RNA sequences to bind to them with low off-target activity. Alternatively, the guide RNA sequences can be directly provided.&#x20;

#### Web Interface Links

[ELSA Calculator Design Mode](https://www.denovodna.com/software/design\_elsa\_calculator)

## ELSA Calculator Design Mode

### **Inputs**

**Title:** the name of your design job \[optional]

**"Automatic Design of Guide RNA Sequences":** when selecting this option, a list of target DNA sequences is provided. The ELSA Calculator will then design multiple guide RNA sequences per target sequence (targeting either the coding strand, the template strand, or both strands, depending on your choice) according to the availability of canonical PAM sites.The guide RNA sequences are ranked by their on-target and off-target activities and only ones that exceed a target threshold are utilized in arrays.

**"Enter Your Own Guide RNA Sequences":** when selecting this option, a list of guide RNA sequences is directly provided.

**"Design for Prokaryotes":** In prokaryotic organisms, extra-long sgRNA arrays will contain one promoter, one sgRNA handle, one transcriptional terminator, and one neutral DNA spacer per unit.&#x20;

**"Design for Eukaryotes":** This option is not available yet.&#x20;

**Number of Targeted Genes/Promoters:** when the "automatic design of guide RNA sequences" option is selected, moving this slider will alter the number the DNA sequence regions that are targeted for sgRNA binding.&#x20;

**Number of Guide RNAs:** when the "Enter Your Own Guide RNA Sequences" option is selected, moving this slider will alter the number the single-guide RNAs expressed inside the extra-long sgRNA array.&#x20;

**Host Organism:** the species used to express the extra-long sgRNA array, selectable from a long list (start typing to narrow down your choices).

**Select Strand for Guide Targeting:** when the "automatic design of guide RNA sequences" option is selected, guide RNA sequences will be designed to bind to either the coding strand, template strand, or both strands, according to this selection. In general, a deactivated Cas:sgRNA complex that targets the template strand will inhibit transcriptional initiation and elongation from a forward promoter. A deactivated Cas:sgRNA complex that targets the coding strand will inhibit transcriptional initiation and elongation from a reverse promoter. An active Cas:sgRNA complex will cleave DNA when bound to either strand.&#x20;

**Target Sequence:** when the "automatic design of guide RNA sequences" option is selected, enter the nucleotide sequence for each targeted DNA region (gene, promoter, etc).&#x20;

**Number of sgRNAs Regulating each Target:** when the "automatic design of guide RNA sequences" option is selected, enter the number of sgRNAs that should be designed to bind to the corresponding target sequence. sgRNAs will be designed to have high on-target activity, low off-target activity, and sufficiently long distances between adjacent binding sites.&#x20;

**Guide RNA Sequence:** when the "Enter Your Own Guide RNA Sequences" option is selected, the nucleotide sequence of the guide RNA portion of the single-guide RNA (commonly 20 nucleotides long).

### Advanced Options

**Maximum Repeat Size:** the maximum allowed length of any repetitive DNA sequence in the ELSA.

**Activate Quick Mode:** when selected, the ELSA Calculator will re-use previously optimized array scaffolds that contain maximally non-repetitive combinations of promoters, sgRNA handles, transcriptional terminators, and neutral DNA spacers. The guide RNA sequences will be inserted into the optimized scaffolds. By default, this option is selected **YES**. If the guide RNA sequences have similar sequences to the other genetic parts in the array, then it would be worthwhile to deactivate quick mode and re-run the design job.

**5' Homology Arm:** a nucleotide sequence that appears upstream of the designed Extra-long sgRNA array. The ELSA Calculator algorithm will avoid introducing any repetitive DNA with the homology arm sequences.

**3' Homology Arm:** a nucleotide sequence that appears downstream of the designed Extra-long sgRNA array. The ELSA Calculator algorithm will avoid introducing any repetitive DNA with the homology arm sequences.

### Outputs

**sgRNA Binding Site Predictions:** the first table lists all the sgRNAs designed to target the selected regions. For each designed sgRNA, the following characteristics are shown:

1. Target Region, the target region ID number (corresponding to the input order)
2. sgRNA #, the sgRNA ID number (a unique number for each sgRNA, counting up)
3. Guide RNA, the nucleotide sequence of the guide RNA portion of the sgRNA
4. Overall Off-target Binding Activity, the cumulative off-target activity of each sgRNA across the selected organism's genome (as quantified as the natural logarithm of the off-target partition function, higher = more off-target activity).&#x20;

_Click "Export to CSV/Excel" to download the full list in the first table._

The second table lists all the on-target and off-target sites for the designed sgRNAs across the inputted target regions and selected organism's genome. For each sgRNA binding site, the following characteristics are shown:

1. sgRNA #, the sgRNA ID number (a unique number for each sgRNA, counting up)
2. Guide RNA, the nucleotide sequence of the guide RNA portion of the sgRNA
3. \# Mismatches, the number of mismatches between the guide RNA and sgRNA binding sites (generally, more mismatches = lower affinity binding)
4. Target Sequence, the nucleotide sequence of the sgRNA binding site
5. Target PAM, the protospacer adjacent motif (PAM) site for the sgRNA binding site. Here, we show the extended 4-nucleotide sequence. NGGN is the canonical 4-nt PAM for Cas9 (S. pyogenes).&#x20;
6. Location, the position of the sgRNA binding site in the target sequence. Each chromosome of an organism is considered a separate target sequence.
7. Source DNA, the name of each separate target sequence, either the Target ID# or the NCBI accession number of the selected organism's chromosome.&#x20;
8. dG\_target, the total binding free energy of the Cas:sgRNA complex to the target site (kcal/mol)
9. dG\_PAM, the binding free energy contribution for the Cas-PAM DNA interaction
10. dG\_exchange, a free energy penalty for mismatches between the guide RNA and target DNA site, taking into account the mismatch positions
11. dG\_supercoiling, the free energy needed to coil or uncoil the DNA site for R-loop formation
12. LogZ, the natural logarithm of the off-target partition function, which is the cumulative sum of off-target activity for each sgRNA

_Click "Export to CSV/Excel" to download the full list in the second table._

**Multiple ELSA Designs:** the list of Extra-long sgRNA Arrays designed by the ELSA Calculator. Each ELSA design is equally optimal with different characteristics. These characteristics are:

1. Number of genetic parts
2. The maximum repeat length, nucleotides (smaller = more non-repetitive = more genetically stable)
3. Average site distance, the average distance between adjacent sgRNA binding sites in nucleotides. If guide RNA sequences are provided, the average site distance is not calculated and is listed as 0.
4. Off-target binding, the natural logarithm of the off-target partition function, which is the cumulative sum of off-target activity for each sgRNA.

_**Select an ELSA design to examine it further.**_&#x20;

**ELSA Part Compositions:** the names and nucleotide sequences for each part in the selected ELSA design.

**ELSA Sequence:** the nucleotide sequence of the full ELSA. **Click "Download Genbank"** to download a highly annotated version of the nucleotide sequence in Genbank format.&#x20;

**DNA Hybridization:** two plots: one plot showing the GC content (the average GC content over a 20 base pair window) for each position in the DNA fragment, and another plot showing dGC (the change in GC content over a 100 base pair window) for each position in the DNA fragment. A separate plot showing the double-stranded DNA melting temperature (the average melting temperature over a 20 base pair window). The average and standard deviation of the DNA fragment's average melting temperature (20 base pair window) is listed. Warnings are listed when the DNA fragment ends have distinctly different melting temperatures and when there are regions that exceed the minimum or maximum melting temperature criteria.&#x20;

**Repetitive DNA Sequences:** the longest repetitive sequence in the DNA fragment, the repeat distribution (the number of repetitive sequences with different lengths), and a repeat chord diagram illustrating the locations of the repetitive sequences. A full list of repeats is also shown, including their types, lengths, and sequences.&#x20;

