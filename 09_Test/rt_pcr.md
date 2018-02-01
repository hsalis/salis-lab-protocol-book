# RT-qPCR

`PROTOCOL DUMP PLEASE FORMAT`

Important Principles to Remember

1. Perform the reaction setup in a clean hood that was not used for the RNA extraction.

2. Use RNAse free pipettes, tips, etc for setting up the reaction.

3. Maintain RNAse free environment using RNAse away and disposable sleeves and lab coat.

Protocol

1. Add 180 uL DEPC water to each sample to bring the concentration to 10 ng/uL Total RNA and 25 ng/uL Yeast tRNA.

2. Prepare RT master mix on ice \(RT Kit: Applied Biosystems/ThermoFisher4368814\).

|  | For 15 uL Sample | Total Volume for 18 Reactions | For 22.5 uL Sample | Total Volume for 17 Reactions |
| :--- | :--- | :--- | :--- | :--- |
| 10x RT Buffer | 3 uL | 54 uL | 4.5 uL | 76.5 uL |
| 25x dNTP Mix | 1.2 uL | 21.6 uL | 1.8 uL | 30.6 uL |
| 10x RT Random Primers | 3 uL | 54 uL | 4.5 uL | 76.5 uL |
| Nuclease Free Water | 6.3 uL | 113.4 uL | 9.45 uL | 160.65 uL |
| Multiscribe Reverse Transcriptase\* | 1.5 uL | 25.5 uL | 2.25 uL | 36 uL |

\*Before adding remove 13.5 uL/20.25 uL for a control.

1. Pipet 15 uL/22.5 uL of master-mix into each PCR tube for each reaction.

2. Pipet 15 uL/22.5 uL of diluted RNA into each PCR tube.

3. Spin down tubes.

4. Put PCR tubes into Thermocycler and run the following procedure. Set thermocycler to respective reaction volumes.

|  | Step 1 | Step 2 | Step 3 | Step 4 |
| :--- | :--- | :--- | :--- | :--- |
| Temperature \(C\) | 25 | 37 | 85 | 4 |
| Time \(Minutes\) | 10 | 120 | 5 | Infinity |

### qPCR Plate Setup

Important Principles to Remember

1. Use 0.1 ml 96 well plates from the Gene Core Facility that are specific for the StepOne Machine\(PN \#4346906\).

2. Since the the sample is now cDNA, RNAse Away no longer needs to be used.

Master mix for qPCR reaction

|  | Single Reaction | Three Replicates \(x 4\) | Master mix 1Iman’s GFP \(x18x4\) | Master mix 316s \(x16x4\) |
| :--- | :--- | :--- | :--- | :--- |
| TaqMan Gene Expression Probe \(20x\) | 1 uL | 4 uL | 72 uL | 64 uL |
| TaqMan Gene Expression Master Mix \(2x\)\* | 10 uL | 40 uL | 720 uL | 640 uL |
| cDNA | 3.5 uL | 14 uL |  |  |
| RNAse Free Water | 5.5 uL | 22 uL | 396 uL | 352 uL |
| Total Volume | 20 uL | 80 uL |  |  |

\*Applied Biosystems4324018

1. Make Mastermix 1 for both probes.

2. Add 66 uL of master mix 1 to individual PCR tubes.

3. Add 14 uL of the respective cDNA to each tube.

4. 1. Vortex cDNA to ensure homogeneity of samples when adding to each master mix.
5. Aliquot 20 uL in 3 wells for each probe/DNA sample.

6. For the primer efficiency runs, add twice Master mix 1 to each PCR tube \(132 uL for each probe\).

7. 1. Aliquot 16.5 uL of Master mix 2 into 6 wells for each probe.

   2. For the first well add 3.5 uL of cDNA like normal.

   3. For the rest prepare 5 tubes with 90 uL of water and for each dilution take 10 uL of the previous sample and add to the water to do a 1:10 dillution.

   4. Add 3.5 uL of each of these dilutions to the plate
8. Seal plate with film.

### Running qPCR on the Step One

1. Spin down the plate with the plate spinner in the Core Facility.

Amplified in Step One real-time machine with this protocol:

50oC  for 2 min

95oC  10 min

40 repeats of 95oC 15 sec, 60oC 1 min.

Use optical plates and caps or adhesive covers.

StepOne Plus Protocol:

Click on StepOne V2.3 icon.  Log on as Deb, click ok.

Click on Advanced Set up.  In the Experiment Properties Tab, select StepOne Plus Instrument \(96 wells\), Quantitation \(standard curve\), TaqMan Reagents, and Standard.

In the Plate Setup Tab, go to Define Targets.  Highlight the target listed and delete.  Then click on Add Saved Target. Select correct Target, click on Add Selected.

Under Assign Targets and Samples, Highlight the wells with samples and click on the assign box for the Target.  Then click on Define and Set Up Standards.  Enter the info \(number of points and replicates, starting quantity\). Click Apply and Close.

In the Run Method Tab, delete the 50o Step.  The run protocol is:

95oC 10 min

40 cycles of 95oC for 15 sec and 60oC for 1 min.

Click on Start Run and Save the file as your name and the date.

When the run is done you will need to check the threshold, make sure it is in the middle third of the line.  Then click Analyze.  Next click on Export.  Click on Customize Export.  Only select the Well, Sample Name, Target Name, Task, Ct and Quantity Columns.  Click Start Export.

### FTP with GeneCore Facility

You will need to use an FTP client to connect. One may already be installed on your system under a name such as Fetch, FileZilla or Cyberduck.

Login information:

Hostname:[hiseq.huck.psu.edu](http://hiseq.huck.psu.edu/)

Username: howard-salis

Password: mk78wsxz

