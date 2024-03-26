# Non-Repetitive Parts Calculator

## Summary

The Non-Repetitive Parts Calculator is a design algorithm that generates toolboxes of highly non-repetitive genetic parts according to user-specified sequence, structure, and model-based constraints.&#x20;

#### Web Interface Links

[Non-Repetitive Parts Calculator Finder Mode](https://www.denovodna.com/software/nrp\_calculator\_finder)

[Non-Repetitive Parts Calculator Maker Mode](https://www.denovodna.com/software/nrp\_calculator\_maker)

## Non-Repetitive Parts Calculator Finder Mode

### **Inputs**

**Title:** the name of your design job \[optional]

**List of Genetic Part Sequences:** upload a file in CSV, FASTA, or text format that contains a list of genetic part names and sequences.&#x20;

**Maximum Repeat Size:** the maximum allowed length of any repetitive DNA sequence.

**Background Sequence:** any nucleotide sequence that must not have any repeats with the non-repetitive genetic parts. The background sequence can be a plasmid or genome sequence to avoid accidentally introducing other repetitive sequences into the organism.

### Outputs

**Non-Repetitive Genetic Part Toolboxes:** a list of genetic part toolboxes with varied amounts of non-repetitiveness, as quantified by their maximum repeat length (a lower maximum repeat length = more non-repetitive). _**Click on a genetic part toolbox to examine it further.**_&#x20;

**Non-Repetitive Genetic Part Sequences:** a list of non-repetitive genetic part names and sequences for the selected genetic part toolbox. _**Click "Export to CSV/Excel" to download the full list.**_

## Non-Repetitive Parts Calculator Maker Mode

### **Inputs**

**Title:** the name of your design job \[optional]

**DNA/RNA Sequence Constraint:**  a degenerate nucleotide sequence that controls which nucleotides are allowed to be selected at each position during non-repetitive genetic part design. Degenerate nucleotides follow the [nucleotide IUPAC code](iupac-codes.md#iupac-nucleotide-code) (ATCGUSRMWKYVBDHN allowed).

**RNA Structure Constraint:** an essential RNA structure written in [dot-bracket-x notation](iupac-codes.md#rna-structural-constraint-notation). When provided, all non-repetitive genetic parts are treated as RNAs that are required to fold into an RNA structure that satisfies the constraint (at thermodynamic equilibrium). The thermodynamic stability of the RNA structural constraint will determine the ensemble of folded structures, including how much of the RNA folds into the desired structure versus alternative structures.&#x20;

**"Design the Largest Possible Genetic Part Toolbox":** when selected, the algorithm will continue the design process until either 1 million non-repetitive genetic parts are designed or when the stopping criteria has been reached (approximately, no more non-repetitive parts are possible).&#x20;

**Target Number of Non-Repetitive Genetic Parts:** the number of desired non-repetitive genetic parts when the "Design the Largest Possible Genetic Part Toolbox" box is not selected.&#x20;

**Maximum Repeat Size:** the maximum allowed length of any repetitive DNA sequence.

**Background Sequence:** any nucleotide sequence that must not have any repeats with the non-repetitive genetic parts. The background sequence can be a plasmid or genome sequence to avoid accidentally introducing other repetitive sequences into the organism.

### Advanced Options

**Exclude Restriction Enzyme Sites:** select restriction enzymes from an auto-complete list (start typing to narrow down choices). The restriction enzymes' recognition sequences will be excluded from the designed non-repetitive genetic parts. \[optional]

**GC% Min and Max:** design non-repetitive genetic parts that have GC content (%) within the selected minimum to maximum range. \[optional, default is 0 to 100% range].&#x20;

**"Allow Internal Repeats":** when selected, allow designed genetic parts to have a repeat sequence within the same part. Useful when a genetic part is very long or when a specific repeat sequence is important to its function. \[optional, default is No].&#x20;

**"Reduce Synthesis Complexity":** when selected, exclude DNA sequences that are difficult to synthesize (e.g. homopolymer sequences and sequence regions with extreme melting temperatures). \[optional, default is No].&#x20;

### Outputs

**Non-Repetitive Genetic Part Toolboxes:** a list of genetic part toolboxes with varied amounts of non-repetitiveness, as quantified by their maximum repeat length (a lower maximum repeat length = more non-repetitive). _**Click on a genetic part toolbox to examine it further.**_&#x20;

**Design Constraint Checker:** an analysis of the specified design constraints that identifies which portions of the sequence or structural constraint are limiting the number of non-repetitive genetic parts.&#x20;

**Non-Repetitive Genetic Part Sequences:** a list of non-repetitive genetic part names and sequences for the selected genetic part toolbox. _**Click "Export to CSV/Excel" to download the full list.**_

## Relevant Articles

[Hossain A., Halper S., Cetnar D., Reis A., and Salis H.M. Automated design of thousands of nonrepetitive parts for engineering stable genetic systems. Nature Biotechnology. v38, p1466–1475. (2020).](https://www.nature.com/articles/s41587-020-0584-2)
