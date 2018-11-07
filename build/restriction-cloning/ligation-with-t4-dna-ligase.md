# Ligation with T4 DNA Ligase

DNA ligation is the process of joining together two DNA molecule ends \(either from the same or different molecules\). Specifically, it involves creating a phosphodiester bond bond between the 3' hydroxyl of one nucleotide and the 5' phosphate of another. This reaction is usually catalyzed by a DNA ligase enzyme. This enzyme will ligate DNA fragments having blunt or overhanging, complementary, 'sticky' ends. Typically, it is easier to ligate molecules with complementary sticky ends than blunt ends. T4 DNA ligase is the most commonly used DNA ligase for molecular biology techniques and can ligate 'sticky' or blunt ends. See the protocol on [digestion](restriction-enzyme-digestion.md) reactions for more details.

## Definitions

* Vector DNA: the fragment of DNA that is used as a vehicle to artificially carry foreign DNA into another cell, where it can be replicated and/or expressed. For nearly all applications in this lab, your vector is a plasmid, which is a small DNA molecule \(circular\) that bacteria can take up from their surrounding environment \([transformation](../transformation-and-integration/)\), replicate and express genes from independently from their chromosome \(i.e. genome\). Plasmid vectors have, at a minimum, a origin of replication \(ORI\), which is a region of DNA that governs that plasmid's copy number, or the number of copies the cell will express it at. We use a number of different vectors in our lab. See the table below for some examples.

| Vector Name | ORI | Copy Number |
| :--- | :--- | :--- |
| pUC | pMB1 \(derivative\) | ~500-700 |
| pColE1 | ColE1 | ~15-20 |
| pACYC | p15A | ~10-12 |
| pSC101 | pSC101 | ~5 |

Plasmids also often have antibiotic resistance genes. Consult with senior students and your plasmid map to see what antibiotic you should be using for selection.

* Insert DNA: the fragment of DNA that will be added to your cloning vector.

## Protocol

For most applications, we use NEB provided T4 DNA Ligase \(M0202\).

1. Set up the following reaction in a PCR tube \(enzymatic reactions tube\) on a rack. Note: _T4 DNA Ligase should be added last_. For all enzymatic reactions, a good strategy is to add inerts first, then valuable components, and then add the enzyme last to "begin" the reaction. This means add components in the following order: water, buffer, DNA parts, T4 DNA Ligase.

| COMPONENT | 20 µL REACTION |
| :--- | :--- |
| T4 DNA Ligase Buffer \(10X\)\* | 2 µL |
| Vector DNA \(4 kb\) | 50 ng \(0.020 pmol\) |
| Insert DNA \(1 kb\) | 37.5 ng \(0.060 pmol\) |
| Nuclease-free water \(ddH2O\) | to 20 µL |
| T4 DNA Ligase | 1 µL |

\*_The T4 DNA Ligase Buffer should be thawed and resuspended at room temperature._

The amounts of DNA to add will vary depending on the vector/insert lengths and the expected ligation efficiency. Variables that could effect your ligation efficiency include what type of sticky ends you have, if you have blunt ends, what is the purity of the DNA sample, and so on. Consult with senior students in the lab if you have questions. The numbers provided for the amounts of DNA above are an example for a vector DNA fragment of length 4 kb, and an insert DNA fragment of length 1 kb. See "Tips for Maximizing Ligation Efficiencies" below to see tips on how much DNA you should add.

**How do I calculate molarity if the Nanodrop provides a mass density?**

Great question! The approximate formula that we use to convert from ng/uL to fmol/uL is as follows. This formula approximates the average molecular weight of a DNA molecule per base pair as 6.6 x 10^-4 ng/fmol-bp.

Y fmol/uL = X ng/uL \* 1515/\(length of DNA fragment\)

1. Gently mix the reaction by pipetting up and down and microfuge briefly \(optional\).
2. For cohesive \(sticky\) ends incubate at room temperature \(at your bench\) for 10 minutes, or optionally incubate at 16 deg. C overnight.
3. For blunt ends or single base overhangs, incubate at 16 deg. C overnight or room temperature for 2 hours \(_alternatively, high concentration T4 DNA Ligase can be used in a 10 minute ligation_\).
4. Perform a [PCR cleanup](../dna/pcr-cleanup.md), eluting with 5 uL ddH2O. You can then transform 0.5-2 uL of the reaction into a 50/55 uL aliquot of competent cells following one of the [transformation protocols](../transformation-and-integration/).

## Tips for Maximizing Ligation Efficiencies

The following tips will help to achieve maximum results from your ligation reactions. These tips are a compilation of student advice and New England BioLabs tips found [here](https://www.neb.com/tools-and-resources/usage-guidelines/tips-for-maximizing-ligation-efficiencies).

* T4 DNA Ligase Buffer should be thawed on the bench or in the palm of your hand, and not at 37°C \(to prevent breakdown of ATP\).
* Once thawed, T4 DNA Ligase Buffer should be placed on ice.
* Ligations can be performed in any of the four standard restriction endonuclease NEBuffers or in T4 Polynucleotide Kinase Buffer \(NEB \#B0201\) if they are supplemented with 1 mM ATP.
* When supplementing with ATP, use ribo ATP \(NEB \#P0756\). Deoxyribo ATP will not work.
* Before ligation, completely inactivate restriction enzyme by heat inactivation, spin column \(NEB \#T1030\), or Phenol/EtOH purification. \(We use Zymo Spin I columns for cleanup of the digestion reactions\).
* Keep total DNA concentration between 1-10 µg/ml.
* Vector: Insert molar ratios between 1:1 and 1:10 are optimal for single insertions \(up to 1:100 for short adaptors\). Insert: vector molar ratio should be 6:1 to promote multiple inserts. You can use NEBioCalculator to calculate molar ratios. A good standard is 10 fmol vector and 1000 fmol insert.

