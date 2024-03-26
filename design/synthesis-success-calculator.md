# Synthesis Success Calculator

## Summary

The Synthesis Success Calculator is a model that predicts whether a DNA fragment can be readily synthesized with a short turnaround time. DNA fragment synthesis is a key step in Synthetic Biology's design-build-test-learn cycle. Unexpected delays or cancellations in the synthesis process create significant bottlenecks to engineering genetic systems. The Synthesis Success Calculator also identifies sequence determinants responsible for synthesis delays & failures, enabling the automated redesign of the genetic system for more rapid synthesis.&#x20;

#### Web Interface Links

[Synthesis Success Calculator Predict Mode](https://www.denovodna.com/software/predict\_synthesis\_success\_calculator)

## Synthesis Success Calculator Predict Mode

### **Inputs**

**Title:** the name of your design job \[optional]

**DNA Fragment Sequence:** the nucleotide sequence of a single DNA fragment. ATCGU nucleotides allowed.

### Outputs

**Predicted Synthesis Outcome:** Success or Failure (delayed/cancellation)

**Predicted Probability of Synthesis Success:** the model-predicted score for synthesis success (the threshold for Success is 0.50).&#x20;

**Overall Sequence Determinant Scores:** the individual contributions of each sequence determinant to the model-predicted score. Contributions are:

1. Long Repetitive Sequence
2. 9-mer Repeat Density
3. GC-rich DNA hairpins
4. Low GC content (at fragment ends)
5. High Melting Temperatures, M (20 bp window average)
6. Low GC content (20 bp window average)
7. Total GC content
8. Low Melting Temperatures, TM (20 bp window average)
9. DNA Fragment Length

**Repetitive DNA Sequences:** the longest repetitive sequence in the DNA fragment, the repeat distribution (the number of repetitive sequences with different lengths), and a repeat chord diagram illustrating the locations of the repetitive sequences. A full list of repeats is also shown, including their types, lengths, and sequences.&#x20;

**DNA Hybridization:** two plots: one plot showing the GC content (the average GC content over a 20 base pair window) for each position in the DNA fragment, and another plot showing dGC (the change in GC content over a 100 base pair window) for each position in the DNA fragment. A separate plot showing the double-stranded DNA melting temperature (the average melting temperature over a 20 base pair window). The average and standard deviation of the DNA fragment's average melting temperature (20 base pair window) is listed. Warnings are listed when the DNA fragment ends have distinctly different melting temperatures and when there are regions that exceed the minimum or maximum melting temperature criteria.&#x20;

**Highlighted Nucleotide Regions:** the nucleotide sequence of the DNA fragment. Nucleotides are colored when they contain an undesired sequence determinant that will negatively influence synthesis success. &#x20;

## Relevant Articles

[Halper, S. M., Hossain, A., & Salis, H. M. (2020). Synthesis Success Calculator: predicting the rapid synthesis of DNA fragments with machine learning. ACS Synthetic Biology, 9(7), 1563-1571.](https://doi.org/10.1021/acssynbio.9b00460)
