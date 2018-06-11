# Genomic Library Prep

`PROTOCOL DUMP PLEASE FORMAT`

## Purification of blunt-ended plasmid and addition of T-overhang

1. Digest or amplify the vector. The product must not have overhangs. Use either:

\(a\) a restriction enzyme that produces blunt ends;

\(b\) a restriction enzyme that produces overhangs. If the overhang is 5’, add Klenow DNA polymerase. If the overhang is 3’, add T4 DNA Polymerase. Use NEB recommended buffer for enzyme, and add dNTPs to buffer with a final concentration of 120 uM \(60% of normal dNTP concentration for a PCR with Phusion\).

1. In a 1.5 mL microcentrifuge tube, digest 10 ug of vector using above method.

   Mix gently & centrifuge briefly to pull down liquid. Incubate at 37 deg C for 6 hours.

   Run 1-2 ul on agarose gel and ensure complete digestion.

   Add 2 uL of 0.5 M EDTA to terminate reactions. Purify DNA product using a Zymo kit.

2. In a 1.5 mL microcentrifuge, add:

   ```text
   46 uL of blunt-ended, digested vector

   15 uL of 5X Terminal Transferase buffer

   7.5 uL of 10X CoCl2 buffer \(comes with Terminal Transferase\)

   1.5 uL of ddTTP   --  this is dideoxy TTP
   ```

Mix gently. Centrifuge briefly. Incubate 1.5 hours at 37 deg C.

Using di-deoxy nucleotide prevents the extension of the T-tail by any polymerase.

1. Purify T-tailed DNA product using a Zymo spin kit.

This next step will increase T/A cloning efficiency from 70% to 90% by removing any vector that was partly T-tailed or not T-tailed at all.

1. In a 1.5 mL microcentrifuge tube, add:

   ```text
   44 uL of purified T-tailed vector

   5 uL of 10X ligase buffer

   1 uL of T4 DNA Ligase \(400 U / uL\)
   ```

Mix gently. Centrifuge briefly. Incubate for 8 minutes at room temperature.

Add product and 1kbp ladder to 1% agarose gel and separate. Identify the T-tailed vector by its size. You should expect to find both larger and smaller products. The larger products are ligated concatemers \(dimer, trimer, etc\) of T-tailed vector. The shorter products are circular T-tailed vector that will run faster than linear product.

Use a scalpel and cut the linear T-tailed vector from the gel. Use the Zymo gel extraction kit to purify the product.

1. Use the Nanodrop to measure T-vector concentration.  Dilute the sample to reach 25-30 ng/uL.  The ligation reaction for T/A cloning will use 50-60 ng of T-tailed vector.

Sonication of Genomic DNA

Insert sonication protocol here with tips for calibration to desired fragment size, based on starting genome size.

End Repair and A-tailing of DNA Fragments

End repair is the combination of three reactions:

\(a\) T4 DNA polymerase is used to fill in 3’ overhangs to create blunt-ended DNA fragments.

\(b\) Klenow DNA polymerase is used to fill in 5’ overhangs to create blunt-ended fragments.

\(c\) T4 Polynucleotide Kinase \(PNK\) is used to phosphorylate the blunt-ended DNA fragments.

1. In a 1.5 mL microcentrifuge tube, add:

   ```text
   5 ul of 5X T4 Ligase Buffer

   0.8 ul ultrapure water

   2 ul of 10 mM dNTPs

   1 uL of T4 DNA Polymerase \(3 U/ul\)

   0.2 uL of Klenow DNA Polymerase \(5 U / ul\)

   1 uL of T4 PNK \(10 U / ul\)

   Add last:  up to 40 ul of fragmented DNA  \(1 ug DNA maximum\)
   ```

Mix gently. Centrifuge briefly. Incubate at 20 degC for 20-30 minutes. Do not allow reaction to exceed 25 deg C -- T4 DNA Polymerase has a much higher exonuclease activity at higher temperatures.

1. Purify DNA with Zymo spin kit.
2. A-tail the repaired DNA fragments.

This reaction uses the enzyme Klenow exo \(3’ to 5’ exo minus\), which is a \_different\_ enzyme than Klenow DNA polymerase.

In a 1.5 mL microcentrifuge tube, add:

```text
    5 uL of 5X Klenow Buffer

    10 ul of 1 mM dATPs     \(or 4 uL of 2.5 mM dATPs\)

    1 uL of Klenow exo \(3ʼ to 5ʼ exo minus\)

    34 uL of end repaired DNA from previous step
```

Mix gently. Centrifuge briefly. Incubate at 37 deg C for 30 minutes.

1. Purify the A-tailed DNA with a Zymo spin kit.

