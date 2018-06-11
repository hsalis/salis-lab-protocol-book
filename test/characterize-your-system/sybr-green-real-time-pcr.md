# SYBR Green Real-Time PCR

## SYBR Green Real-Time PCR

This protocol is a good alternative to [RT-qPCR](rt-qpcr.md) for quantifying mRNA levels if you have many gene targets \(which would require unique probes for each mRNA - $$$\). You can find all the SYBR Green kits here at [ThermoFisher's website](https://www.thermofisher.com/us/en/home/life-science/pcr/real-time-pcr/real-time-pcr-reagents/sybr-green-real-time-master-mixes.html).

## SYBR Green qPCR Plate Setup

_Important Principles to Remember_

* Use 0.1 ml 96 well plates from the Gene Core Facility that are specific for the StepOne Machine\(PN \#4346906\).
* Since the the sample is now cDNA, RNAse Away no longer needs to be used.

### Master mix for qPCR reaction

|  | Single Reaction | Replicates \(x24\) |
| :--- | :--- | :--- |
| Forward Primer \(300 nM final\) | 2 µL |  |
| Reverse Primer \(300 nM final\) | 2 µL |  |
| SYBR Green Master Mix \(2x\) | 10 µL | 240 µL |
| cDNA | 3 µL | 72 µL |
| RNase Free Water | 3 µL | 72 µL |
| Total Volume | 20 µL | 480 µL |

1. Make Mastermix for the two samples. Vortex cDNA to ensure homogeneity of samples.
2. Dilute primers to 3 uM \(3uL primer + 97 uL water in PCR Strip\)
3. Add 16 uL of master mix to each well.
4. Add 2 uL of each primer to its respective well.
5. Seal plate with film.

### Running qPCR on the Step One

1. Spin down the plate with the plate spinner in the Core Facility.

![](https://lh4.googleusercontent.com/Qm02paARMeM8jcd9wFN-Tl8Q7zKVdKj5ikYtJkUF5jz0cWJkwyilm2L0Ecvwpp19tq4pmIM0cwOQ_vJVIhvW7Yzwug3kZPMmDMUoh2DCaU281WzIFNSNSFyhvvqrYbrrXW5mqIu6)

Set the Anneal Temp to 56.5 C

![](https://lh3.googleusercontent.com/1uQrT1cS16zOMk01vXDxmrXn4ThvBcIfOaxk2DoSfn9As0km_Y3X57-39za1BILNUNo_hkTScyTG_PcsGSy5lnZ7fhAfiedVSuBRGUEwBivW7n2k25DrYrPJ2u7dVN2MIjvVfKYL)

### StepOne Plus Protocol:

1. Click on StepOne V2.3 icon. Log on as Deb, click ok.
2. Click on Advanced Set up. In the Experiment Properties Tab, select StepOne Plus Instrument \(96 wells\), Quantitation \(standard curve\), SYBR Green Reagents, ROX, and Standard. Melt Curve Continuous
3. In the Plate Setup Tab, go to Define Targets. Highlight the target listed and delete. Then click on Add Saved Target. Select correct Target, click on Add Selected.
4. Under Assign Targets and Samples, Highlight the wells with samples and click on the assign box for the Target. Then click on Define and Set Up Standards. Enter the info \(number of points and replicates, starting quantity\). Click Apply and Close.
5. Click on Start Run and Save the file as your name and the date.
6. When the run is done you will need to check the threshold, make sure it is in the middle third of the line. Then click Analyze. Next click on Export. Click on Customize Export. Only select the Well, Sample Name, Target Name, Task, Ct and Quantity Columns. Click Start Export.

### File Transfer Protocol with GeneCore Facility:

You will need to use an FTP client to connect. One may already be installed on your system under a name such as Fetch, FileZilla or Cyberduck.

_Login information_

Hostname: [hiseq.huck.psu.edu](http://hiseq.huck.psu.edu/)

Username: howard-salis

Password: mk78wsxz

