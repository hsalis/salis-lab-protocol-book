# RBS Library Calculator

## Summary

The RBS Library Calculator is a design algorithm for optimizing protein expression in bacteria across a 100,000-fold range. In Predict mode, the RBS Library Calculator predicts how a ribosome binding site (RBS) library changes a protein's expression level. In Design mode, the RBS Library Calculator generates an optimized RBS library (a small number of RBS variants defined by a single degenerate nucleotide sequence) to systematically vary a protein's expression level across a selected range. Additional  design constraints can be used to customize the RBS library, for example, to include restriction sites or a constant upstream sequence.&#x20;

#### Web Interface Links

[RBS Library Calculator Predict Mode](https://www.denovodna.com/software/predict\_rbs\_library\_calculator)

[RBS Library Calculator Design Mode](https://www.denovodna.com/software/design\_rbs\_library\_calculator)

[RBS Library Calculator Multi-Design Mode](https://www.denovodna.com/software/design\_rbs\_library\_calculator\_many)

## RBS Library Calculator Predict Mode

### **Inputs**

**Title:** the name of your design job \[optional]

**RBS Library Sequence:** a degenerate nucleotide sequence using the [nucleotide IUPAC code](iupac-codes.md#iupac-nucleotide-code) (ATCGUSRMWKYVBDHN allowed) specifying multiple RBS library variants.&#x20;

**Protein Coding Sequence:** the nucleotide sequence of the protein coding sequence, starting from the start codon and ending at the stop codon. ATCGU nucleotides allowed.

**Host Organism:** the bacterial species used to express the protein, selectable from a long list (start typing to narrow down your choices).

### Advanced Options

**Constant Upstream Sequence:** a nucleotide sequence that appears upstream of the RBS library (ATCGU nucleotides allowed). Useful when adding upstream restriction sites, ribozymes, or any other mRNA sequence (e.g. a long 5' UTR that should remain unchanged). _**The constant upstream sequence must be part of the mRNA transcript.**_ \[optional]

**Free Energy Model Version:** the free energy model used to carry out predictions. New versions are developed as more interactions are quantitatively characterized and incorporated into the model. \[optional]

### Outputs

**Translation Initiation Rates:** the calculated translation initiation rates for each RBS library variant. The rates are given on a proportional scale ranging from 1 to 100,000+.

**Translation Rate Coverage:** a plot showing the translation initiation rates for each RBS library variant.

**Ribosome Binding Free Energy Calculations:** a detailed table showing the free energy calculations used to predict each RBS library variants' translation initiation rates. Each Gibbs free energy change is the quantification of an interaction between the ribosome and mRNA that affects its translation initiation rate. [Read more about the RBS Calculator's free energy model](rbs-calculator/rbs-calculator-free-energy-model.md).&#x20;

## RBS Library Calculator Design Mode

### **Inputs**

**Title:** the name of your design job \[optional]

**Protein Coding Sequence:** the nucleotide sequence of the protein coding sequence, starting from the start codon and ending at the stop codon. ATCGU nucleotides allowed.

**Target Minimum Translation Initiation Rate:** the lowest translation initiation rate in the desired RBS library on a proportional scale from 1 to 100,000+.

**Target Maximum Translation Initiation Rate:** the highest translation initiation rate in the desired RBS library on a proportional scale from 1 to 100,000+.

**Target Library Size:** the number of sequence variants in the desired RBS library. The RBS Library Calculator will design several RBS libraries, prioritizing ones with your target library size.&#x20;

**Host Organism:** the bacterial species used to express the protein, selectable from a long list (start typing to narrow down your choices).

**"Genome Editing Mode":** activating Genome Editing mode will use an existing RBS sequence (e.g. in the genome of an organism) as the starting point for RBS library design. The algorithm will restrict changes to the existing RBS sequence to a small mutation box, which is necessary for various genome engineering techniques . You may specify the length of the mutation box.&#x20;

**Genomic RBS Sequence:** the nucleotide sequence of an existing RBS sequence that will be modified to generate an RBS library. ATCGU nucleotides allowed. \[only required when using Genome Editing mode].

**Maximize Size of Mutation Box:** the length of a consecutive region in the genomic RBS sequence that can be mutated to design the RBS library (length in nucleotides). \[only required when using Genome Editing mode].

### Advanced Options

**Initial RBS Library Sequence:** a degenerate sequence used to initialize the design of the RBS library. Degenerate nucleotides follow the [nucleotide IUPAC code](iupac-codes.md#iupac-nucleotide-code) (ATCGUSRMWKYVBDHN allowed). Useful when designing RBS libraries with very high maximum translation initiation rates (e.g. entering a previously designed synthetic RBS with a high translation initiation rate as the starting point for RBS library design). \[optional]

**RBS Library Sequence Constraints:** a degenerate nucleotide sequence that controls which nucleotides are allowed to be chosen during RBS library design. Degenerate nucleotides follow the [nucleotide IUPAC code](iupac-codes.md#iupac-nucleotide-code) (ATCGUSRMWKYVBDHN allowed). \[optional]

**Constant Upstream Sequence:** a nucleotide sequence that appears upstream of the RBS library (ATCGU nucleotides allowed). Useful when adding upstream restriction sites, ribozymes, or any other mRNA sequence (e.g. a long 5' UTR that should remain unchanged). _**The constant upstream sequence must be part of the mRNA transcript.**_ \[optional]

**Free Energy Model Version:** the free energy model used to carry out predictions. New versions are developed as more interactions are quantitatively characterized and incorporated into the model. \[optional]

### Outputs

**Multiple RBS Libraries:** several designed RBS libraries with different numbers of RBS sequence variants. Each RBS library is optimized to have large differences in their translation initiation rates, covering the broadest possible range. The degenerate nucleotide sequence and (minimum/maximum) translation initiation rates are shown. _**Click on a RBS library selection to examine it further.**_&#x20;

**Translation Rate Coverage:** a plot showing the translation initiation rates for the selected RBS library and its sequence variants.

**Ribosome Binding Free Energy Calculations:** a detailed table showing the free energy calculations used to predict each RBS library variants' translation initiation rates. Each Gibbs free energy change is the quantification of an interaction between the ribosome and mRNA that affects its translation initiation rate. [Read more about the RBS Calculator's free energy model](rbs-calculator/rbs-calculator-free-energy-model.md).&#x20;

## Relevant Articles

[Reis, A.C. & Salis, H.M. (2020). An automated model test system for systematic development and improvement of gene expression models. ACS Synthetic Biology, 9(11), 3145-3156.](https://doi.org/10.1021/acssynbio.0c00394)

[Farasat, I., Kushwaha, M., Collens, J., Easterbrook, M., Guido, M., & Salis, H. M. (2014). Efficient search, mapping, and optimization of multi‐protein genetic systems in diverse bacteria. Molecular systems biology, 10(6), 731.](https://doi.org/10.15252/msb.20134955)

[Ng, C. Y., Farasat, I., Maranas, C. D., & Salis, H. M. (2015). Rational design of a synthetic Entner–Doudoroff pathway for improved and controllable NADPH regeneration. Metabolic engineering, 29, 86-96.](https://doi.org/10.1016/j.ymben.2015.03.001)



