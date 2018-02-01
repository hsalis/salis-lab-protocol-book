# PCR

A method for amplifying DNA _in vitro_. PCR is a revolutionary method developed by Kary Mullis in the 1980s. PCR is based on using the ability of DNA polymerase to synthesize a new strand of DNA complementary to the offered template strand. Because DNA polymerase can add a nucleotide only onto a preexisting 3'-OH group, it needs a primer to which it can add the first nucleotide. This requirement makes it possible to delineate a specific region of template sequence that the researcher wants to amplify. At the end of the PCR reaction, the specific sequence will be accumulated in billions of copies (amplicons).

### Overview

The steps of PCR visualized in **Figure 1** are as follows:
1. **Denature**, or melt, the DNA to allow separation of your double stranded DNA template into single stranded DNA fragments.
2. **Anneal** the primers to the template DNA.
3. **Extension** of the DNA polymerase to "copy" the template.
4. Repeat steps many times.

<a href="https://github.com/"><center><img src="../figures/pcr.png" width="800"></center></a>

<center><b>Figure 1</b>. The basic steps of PCR.</center>

<p>&nbsp;</p>

Cases when you will use PCR:
* To amplify DNA that you have only a small amount of (e.g. a `gblock`, `PCR assembly product`, etc.)
* To amplify a DNA sequence off of a genome or a plasmid, known as colony PCR.
* To amplify DNA fragments for any of the possible cloning methods (e.g. `Digest-Ligate`, `Gibson Assembly`, `LCR`, etc.)

What you'll be doing for PCR:
1. Design a pair of primers for each amplicon (region of DNA to amplify)
2. Prepare template
3. Prepare PCR mix
4. Run PCR [thermal cycler](../13_Lab_Equipment/thermal_cycler.md) protocol
5. Analyze by [gel electrophoresis](../10_Test/gel_electro.md)

### Primer Design

Primers, as illustrated in **Figure 1**, are relatively short ssDNA oligos that will direct DNA polymerase during the PCR. There are two primers for a PCR reaction. The first primer, also known as the `Forward Primer` (FP), should hybridize to the 5'- end (left) of the `template strand` (the bottom strand in **Figure 1**). This means that the forward primer should be the same sequence as the `coding strand` (top strand in **Figure 1**). The second primer, also known as the `Reverse Primer` (RP), should hybridize to the `coding strand` on the 3'- end (right). This means that the reverse primer _must be_ the reverse complement of the `coding strand`. 

When you design primers, you _must_ follow these rules if you want your PCR to work correctly:

1. Primers should be of similar length. Target 18-30 bp in length for the hybridization region. Specifically, the annealing temperature of the primers works best around 57-60°C. See the tools listed below.

2. "GC clamps" on the 3'- end of the primers. Aim for 2-3 bp of "GC" base pairings on your primer end.

3. Avoid strong DNA structures with ΔG < -5.0 kcal/mol.

4. Avoid self-dimers, or primers that bind to themselves with ΔG < -5.0 kcal/mol.

5. Avoid hetero-dimers, or pairs of primers that bind to each other with ΔG < -5.0 kcal/mol.

6. Primers should not bind to other locations with up to ~5 mismatches.

Tools that we use are listed here. Make sure to use Nearest Neighbor energy models for the melting temperature and structure predictions, as they are most accurate:

* [OligoAnalyzer](https://www.idtdna.com/calc/analyzer)
* [OligoCalc](http://biotools.nubic.northwestern.edu/OligoCalc.html)
* Biopython has a [MeltingTemp Module](http://biopython.org/DIST/docs/api/Bio.SeqUtils.MeltingTemp-module.html) if you want to do things in Python.

Online primer design guidelines and tools can be found [here](https://openwetware.org/wiki/Designing_primers).

You can add 5' tails on your primers. This will introduce extra DNA on the ends of your amplicon. Up to 15-20 bp tails won't really affect the PCR efficiency. Reasons for doing this might be to introduce [restriction enzyme](digestion.md) cut sites to aid in your cloning. NOTE: The annealing temperature is still only calculated by the hybridization of the subsequence of the primer that binds to the DNA template, _not_ the whole primer sequence.


### Choosing the Right DNA Polymerase for YOUR PCR

Refer to [NEB's DNA Polymerase Selection Chart](https://www.neb.com/tools-and-resources/selection-charts/dna-polymerase-selection-chart) and if it suits you, watch their [video](https://www.neb.com/tools-and-resources/video-library/choose-the-right-dna-polymerase-for-pcr). We have used the following DNA polymerases 


### Q5 DNA polymerase

[Q5® High-Fidelity DNA Polymerase](https://www.neb.com/products/m0491-q5-high-fidelity-dna-polymerase#Product%20Information) has 2-fold higher fidelity than its predecessor, [Phusion DNA polymerase](#-Phusion-DNA-polymerase). FOr longer (>1 kb) amplicons, a Q5 PCR with fewer (25) cyclers should be considerd, especially if point mutations have been a problem for this amplicon.

Combine the following reagents together in a PCR tube. Add ddH2O first and Q5 DNA polymerase last. Transfer to the thermocycler and run the protocol as describe below.

COMPONENT | 25 µL REACTION | 50 µL REACTION | FINAL CONCENTRATION
--- | --- | --- | ---
5X Q5 Reaction Buffer | 5 µL | 10 µL | 1X
10 mM dNTPs | 0.5 µL | 1 µL | 200 uM
10 uM Forward Primer | 1.25 µL | 2.5 µL | 0.5 uM
10 uM Reverse Primer | 1.25 µL | 2.5 µL | 0.5 uM
Template DNA | variable | variable | 0.01 - 10 ng
Q5 High-Fidelity DNA Polymerase | 0.25 µL | 0.5 µL | 0.02 U/µL
5X Q5 High GC Enhancer (optional) | (5 µL) | (10 µL) | (1X)
ddH2O | to 25 µL | to 50 µL | 

STEP | TEMPERATURE (°C) | TIME (s)
--- | --- | ---
Initial Denaturation | 98°C | 30 sec
(1) Denature | 98°C | 5-10 sec
(2) Anneal | 50-72°C (Tm+3) | 10-30 sec
(3) Extend | 72°C | 20-30 sec/kb
REPEAT (1-3) | 35 times | N/A
Final Extension | 72°C | 2 min
Hold | 4°C | Forever

[NEB Protocol](https://www.neb.com/protocols/2013/12/13/pcr-using-q5-high-fidelity-dna-polymerase-m0491)


### Phusion DNA polymerase

A legacy polymerase that we sometimes still order. No reason to use this over [Q5 DNA polymerase](#-Q5-DNA-polymerase). The [NEB Protocol](https://www.neb.com/protocols/1/01/01/pcr-protocol-m0530) describes reaction setup and thermal cycler conditions for Phusion.


### Taq DNA polymerase

A cheaper thermo-stable polymerase relative to Q5 and Phusion. Used for small amplicons, [PCR Assembly](pcr_assembly.md), and colony PCR off the genome.

Combine the following reagents together in a PCR tube. Add ddH2O first and Q5 DNA polymerase last. Transfer to the thermocycler and run the protocol as describe below.

COMPONENT | 25 µL REACTION | 50 µL REACTION | FINAL CONCENTRATION
--- | --- | --- | ---
10X ThermoPol Reaction Buffer | 2.5 µL | 5 µL | 1X
10 mM dNTPs | 0.5 µL | 1 µL | 200 uM
10 uM Forward Primer | 0.5 µL | 1 µL | 0.2 uM
10 uM Reverse Primer | 0.5 µL | 1 µL | 0.2 uM
Template DNA | variable | variable | <1,000 ng
_Taq_ DNA Polymerase | 0.125 µL | 0.25 µL | 1.25 units/50 µL PCR
ddH2O | to 25 µL | to 50 µL | 

STEP | TEMPERATURE (°C) | TIME (s)
--- | --- | ---
Initial Denaturation | 95°C | 30 sec
(1) Denature | 95°C | 15-30 sec
(2) Anneal | 45-68°C (Tm+3) | 15-60 sec
(3) Extend | 68°C | 1 min/kb
REPEAT (1-3) | 35 times | N/A
Final Extension | 68°C | 2 min
Hold | 4°C | Forever

[NEB Protocol](https://www.neb.com/protocols/0001/01/01/taq-dna-polymerase-with-thermopol-buffer-m0267)


### Troubleshooting your failed PCR

NEB has a decent [PCR Troubleshooting Guide](https://www.neb.com/tools-and-resources/troubleshooting-guides/pcr-troubleshooting-guide).

1. Test different annealing temperatures. If you have no product, try a lower annealing temperature. If you have too many undesirable products, try increasing the annealing temperature by a few degrees.

2. Check your primer design. Double check for primer dimerization, poor primer specificity, and so forth. Re-design primers and try another primer pair.

3. Is the quality of your template good? If your template is a miniprep, check to see if there is genomic contamination using the [NanoDrop](../13_Lab_Equipment/nanodrop.md).

4. If GC-rich templates, try using the polymerase's appropriate GC enhancer.


### A-Tailing with Taq polymerase

_Taq_ DNA polymerase, in addition to polymerizing the reverse complement of a given template strand, also adds an additional adenosine residue to the 3'-end of the newly-synthesized strand. This is useful for [T/A cloning](). First, amplify your target DNA with a [high-fidelty DNA polymerase](#-Q5-DNA-polymerase), then A-tail with _Taq_, which is lower-fidelty. After performcing a PCR cleanup on the amplicon, combine the following:

COMPONENT | Volume (µL)
--- | ---
DNA (PCR cleanup product) | x µL
ThermoPol Buffer | 5 µL
*dATP (10 mM) | 1 µL
_Taq_ DNA Polymerase | 0.2 µL
ddH2O | to 50 µL

* You can also use 1 µL dNTPs (10 mM), if dATP is not available.

Incubate at 72°C for 20 minutes.

[NEB Protocol](https://www.neb.com/protocols/2013/11/01/a-tailing-with-taq-polymerase)


### Rescue PCR

Rescue PCR is simply a PCR reaction to recover and increase the concentration of a DNA product that you have in very low concentrations. For example, you might do a rescue PCR following a [PCR Assembly](pcr_assembly.md)