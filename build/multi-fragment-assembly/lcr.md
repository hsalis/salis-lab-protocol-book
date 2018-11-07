# LCR

Ligase cycling reaction \(LCR\) is a one-step, scarless DNA assembly method that uses single-tranded bridging oligos complementary to the ends of neighboring DNA parts, a thermostable ligase to join DNA backbones, and multiple denaturation-annealing-ligation temperature cyles to assemble complex DNA constructs. LCR has been shown to enable reliable assembly of up to 12 DNA parts with 60-100% of individual clones being correct \(ref\).

[![](../../.gitbook/assets/pcr.png)](https://github.com/)

**Figure 1**. The basic steps of LCR.

de Kok, S., Stanton, L. H., Slaby, T., Durot, M., Holmes, V. F., Patel, K. G., et al. \(2014\). Rapid and reliable DNA assembly via ligase cycling reaction. ACS synthetic biology, 3\(2\), 97–106. [doi:10.1021/sb4001992](http://pubs.acs.org/doi/10.1021/sb4001992)

This protocol has been adapted from the Karmella Haynes/Cameron Gardner \(2015\) openwetware protocol found [here](lcr.md).

## Part 1. Design the assembled plasmid, bridging oligos, and primers

1. Identify junctions \(or boundaries where DNA fragments will be ligated at\) by combining DNA fragments in a plasmid viewing program to represent your final assembled plasmid.
2. At each junction, select ~20-30 bp leftward on fragment 1 \(from 3’ end\) and another ~20-30 bp rightward on fragment 2 \(from 5’ end\) at each junction \(simply copy the coding DNA sequence as presented in ApE\). Concatenate these two sequences to create your bridge oligo. Make sure to annotate! And repeat for all junctions. You are targeting annealing temperatures of 60-70°C for each _half_ of each bridging oligo. _Note_: If your assembly has one insert and one vector \(for plasmid assembly\), you will have two junctions and will design two bridge oligos. In general for LCR, you will always design n+1 bridging oligos, where n is the number of fragments that will be assembled. All briding oligos should have roughly equivalent annealing temperatures for best results.
3. If needed, design PCR primers as needed to amplify fragments from their templates. See PCR primer design and PCR protocols [here](../dna/pcr.md).

## Part 2. Prepare the bridging oligos

1. Bring the IDT oligo pellet to 100 μM with ddH2O. \( X μL dd2O = Y nmoles oligo \(on tube\) \* 10 \).
2. Make a 300 nM working solution \(final volume = 100 μL\) in a new tube \(0.3 μL of 100 μM oligo stock + 99.7 μL ddH2O\).
3. Use 3.0 μL of working oligo solution per 30 μL LCR reaction.

## Part 3. Prepare the DNA fragments \(PCR & PNK\)

1. Amplify the fragments of interest using 50 uL [PCR](../dna/pcr.md) reactions. make sure to use either Phusion or Q5 DNA polymerase to generate fragments with blunt ends \(other polymerases don't\).
2. Purify products with either a PCR clean up or gel extraction, and measure the concentration with the [NanoDrop](https://github.com/reisalex/salis-lab-protocol-book/tree/453898c9360786eef221e6fffd8409c03a547e50/13_Lab_Equipment/nanodrop.md).
3. Dilute the purified dsDNA fragments to 30 fmol/μL \(30 nM\). \(The volume of purified DNA \(x\) you will need to dilute in a final volume of 50 μL = length in bp ÷ measured ng/μL  _30 fmol/μL_  650 fg/fmol dsDNA ÷ 1,000,000 fg/ng  _50 μL final volume; FORMULA: x μL = length in bp ÷ measured ng/μL_  0.0195 ng/μL \* 50μL\).
4. Mix the appropriate amount of dsDNA fragments together and treat with polynucleotide kinase \(PNK\) to add 5'-phosphates \(see below\). If one or more of your fragments were derived from template plasmids, add 1 uL FastDigest DpnI. DpnI will cut the methylated DNA that came from a bacterial cell \(plasmid template\) and will not cut any synthetic PCR products. We found this was extremely critical to reduce background when we screened colonies following LCR.

| COMPONENT | 10 µL REACTION |
| :--- | :--- |
| PCR product or dsDNA \(2 µL/part\) | up to 8.5 µL |
| 10x T4 DNA Ligase Buffer \(NEB\) | 1.0 µL |
| T4 PNK \(NEB\) | 0.5 µL |
| DpnI \(if fragment from plasmid\) | 1 µL |
| ddH2O | to 10 µL |

* Incubate at 37°C for 30 min.
* Heat-in

| STEP | TEMPERATURE \(°C\) | TIME |
| :--- | :--- | :--- |
| Incubate | 37°C | 30 min\* |
| Heat-inactivate PNK | 65°C | 20 min |

\*Incubate for 36 hours if you added DpnI. We found that this is necessary to significantly reduce background. DpnI is more than an order of magnitude slower in digesting hemi-methylated DNA.

## Part 4. Perform LCR

Add components to the PNK DNA reaction as described in the table below, transfer to the thermal cycler and run the protocol below. Follow LCR with a [PCR Clean-Up](../dna/pcr-cleanup.md), elute with 5 µL, and transform into a cloning strain \(DH10B\).

| COMPONENT | 30 µL REACTION | CONCENTRATION |
| :--- | :--- | :--- |
| PNK DNA reaction | 10 µL | 3 nM each fragment |
| Briding Oligo | 3 µL \(each\) | 30 nM each |
| 10X Ampligase or _Taq_ ligase buffer | 3.0 µL |  |
| Ampligase \(or _Taq_\) ligase | 1.0 µL |  |
| ddH2O | to 30 µL |  |

| STEP | TEMPERATURE \(°C\) | TIME |
| :--- | :--- | :--- |
| Initial Denature | 94°C | 2 min |
| 1. Denature | 94°C | 10 sec |
| 2. Anneal | Tm - 10°C | 30 sec |
| 3. Ligate | 65°C | 60 sec |
| Go to 2 x30 |  |  |
| Hold | 4°C | inf |

## Tips

* When PCR amplifying the backbone vector fragment, add 0.1-0.3ng of original plasmid to PCR mix \(adding too much original plasmid will result in higher background\)
* When designing the bridging oligos, follow the same rules as [PCR primer design](../dna/pcr.md#primer-design), as the same principles apply.

