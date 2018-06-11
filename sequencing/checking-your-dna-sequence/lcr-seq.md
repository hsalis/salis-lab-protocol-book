# LCR-seq

`PROTOCOL DUMP PLEASE FORMAT`

Developed by Sean Halper, 2016

Method for optimizing sequencing of large/genome integrated constructs via LCR

Part 1: Design assembled construct, primers and bridging oligos

1. Identify and select unique sequences \(18-25 bp\) upstream and downstream \(30-100 bp\) of the regions you are interested in sequencing. These sequences will become your colony PCR/sequencing primers. Tm of at least 58 C \(60+ preferrable\)
2. Identify junctions \(or boundaries where DNA fragments will be ligated at\) by combining DNA fragments in ApE to represent your final assembled construct.

Note: You will need to include additional nucleotides to those regions of interest closest to your sequencing primer, since the sequencing has a run up of 100-150 bp before an accurate read. Additionally, Quintara sequencing reads are unreliable beyond 700 bp, so plan your construct designs accordingly \(multiple run ups for multiple seq primers\) .

1. Select ~20-30 bp leftward on fragment 1 \(from 3’ end\) and another ~20-30 bp rightward on fragment 2 \(from 5’ end\) at each junction \(simply copy the coding DNA sequence as presented in ApE\). Concatenate these two sequences to create your bridge oligo. Make sure to annotate! And repeat for all junctions. Tms of 60-70 deg C.

Part 2: Phusion Colony PCR

We use Phusion for the colony PCRs \(instead of the usual Taq\) since Phusion produces blunt ended PCR products, which are required for the downstream LCR to work

1. Pick colony from plate with toothpick/pipette tip and suspend colony in 100 uL ddH2O. Alternatively, dip pipette tip in overnight culture and immediately dip into 100 uL ddH2O.

Note: colony/ liquid culture should be as fresh as possible for best downstream results

1. Vortex suspended colony for 60 seconds.
2. Phusion colony PCR

|  |  |  | Reaction ingredients |  | Thermal cycler protocol\(in development\) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Reagent | Volume |  | Step | Temperature \(C\) | Time |
| Suspended colony | 10 μL |  | 1. Initial Denature | 98 | 10 min |
| Forward/reverse Primers | 0.5 \(each\) |  | 2. Denature | 98 | 10 sec |
| 5X HF Buffer | 10.0 |  | 3. Anneal | Tm | 30 sec |
| dNTPs | 1.0 |  | 4. Extend | 72 | 60 sec |
| Phusion | 0.25 - 0.5 |  | Go to 2 \(x30\) |  |  |
| dH2O | 27.75 μL |  | 5. Final Extension | 72 | 5 min |
| \(total volume\) | 50.0 μL |  | Hold | 4 | 00 |

1. Gel extract bands at lengths determined by your construct, PCR clean-up and elute in 20 uL H2O.

Part 3: LCR

1. Follow LCR Protocol for steps 2-4 with the following adjustments:
2. 1. Colony PCRS \(from Part 2 of this protocol\) for amplifying the dsDNA in Part 3 of the LCR protocol
   2. PNK reaction scaled for number of parts you are ligating

| Reagent | Volume |
| :--- | :--- |
| Clean PCR or dsDNA \(2 μL/part\) | X μL |
| 10x T4 DNA Ligase Buffer \(NEB\) | 0.1\*X μL |
| T4 PNK \(NEB\) | 0.05\*X μL |
| \(total volume\) | ~10 \(1.15\*X\) μL |

1. LCR reaction scaled for number of parts you are ligating

|  |  |  | Reaction ingredients |  | Thermal cycler protocol\(in development\) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Reagent | Volume |  | Step | Temperature \(C\) | Time |
| PNK DNA | ~10 μL |  | 1. Initial Denature | 94 | 2 min |
| Oligo Bridge | 3.0 \(each\) |  | 2. Denature | 94 | 10 sec |
| 10X Ampligase Buffer | ~3.0 |  | 3. Anneal | 55 | 30 sec |
| Ampligase \(or Taq\) | 1.0 |  | 4. Ligate | 55 | 5 min |
|  |  |  | Go to 2 \(x30\) |  |  |
| \(total volume\) | ~30.0 μL |  | Hold | 4 | 00 |

Part 4: Exonuclease and Rescue PCR

1. After the LCR finishes, add 3.5μL 10X ExoI buffer and 0.5 Exonuclease I. Exonuclease I removes ssDNA \(bridging oligos and primers\) from the reaction mixture prior to the rescue PCR Return to the thermocycler for 1hr @ 37C, 20 min @ 80C and forever @ 4C.
2. Perform a PCR cleanup on the LCR mixture, and elute with 10 μL ddH2O.
3. Perform a rescue PCR on the eluted DNA:

|  |  |  | Reaction ingredients |  | Thermal cycler protocol\(in development\) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Reagent | Volume |  | Step | Temperature \(C\) | Time |
| LCR Product | 10 μL |  | 1. Initial Denature | 98 | 10 min |
| Forward \(first\) / Reverse \(last\) Primers | 0.5 \(each\) |  | 2. Denature | 98 | 10 sec |
| 5X HF Buffer | 10.0 |  | 3. Anneal | Tm +3 | 30 sec |
| dNTPs | 1.0 |  | 4. Extend | 72 | 60 sec |
| Phusion | 0.25 - 0.5 |  | Go to 2 \(x30\) |  |  |
| dH2O | 27.75 μL |  | 5. Final Extension | 72 | 5 min |
| \(total volume\) | 50.0 μL |  | Hold | 4 | 00 |

1. Perform gel extraction and final PCR cleanup on amplified band, elute in 10-20μL of water.

Note: Rescued bands tend to run 200-300 bp shorter than their final length, so don’t panic if they seem short. Shortness beyond that is probably an off target ligation product, which you don’t want to sequence.

1. Send LCR band for sequencing to determine the band.

