# Microplate fluorescence measurements

`PROTOCOL DUMP PLEASE FORMAT`

### Steady-State Growth and Fluorescence Measurements

Fluorescent proteins are versatile reporters that enable the measurement ofin vivoprotein expression levels. The following protocol describes the usage of spectrophotometers and/or flow cytometry to record fluorescent protein expression levels fromE. colicultures in 96-well microplate format. Importantly, our protocol uses long culture times of 24 to 36 hours to achieve steady-state conditions so that the average number of proteins per cell is constant over time. This protocol improves the measurement precision, day-to-day and lab-to-lab reproducibility, and enables a more accurate comparison between model predictions and experimental data.

### 

### TECAN

1.A 96 deep well microplate containing 700 µL LB media and selective antibiotic is inoculated from single colonies. A non-fluorescent \(white\) cell culture is also inoculated. Cultures are grown overnight at 37°C with 250 r.p.m orbital shaking to an optical cell density \(OD600\) of 2.0.

1. A fresh 96-well transparent, flat bottom microplate is filled with 198 µL M9 minimal media \(;1X M9 salts: 6.8 g/L Na2PO4, 3 g/L KH2PO4, 0.5 g/L NaCl, 1 g/L NH4Cl; 2 mM MgSO4, 100 µM CaCl2, selective antibiotic; and 0.4% glucose, adjusted to a pH of 7.4\). Microplate wells are inoculated by overnight cultures using a 1:100 dilution. The microplate is placed inside the spectrophotometer and incubated at 37°C with 250 r.p.m orbital shaking.

1. The spectrophotometer records OD600 and fluorescence measurements every 10 minutes. These measurements are used to calculate cell growth rates and steady-state bulk fluorescence per OD600.

1. Once a culture reaches an OD600 between 0.15 and 0.20, 10 to 20 µL samples of each culture are transferred to fresh transparent, flat bottom microplates containing 180 to 190 µL pre-warmed M9 minimal media and selective antibiotic \(a 1:5 to 1:10 dilution\). The new microplate is placed inside the spectrophotometer and incubated at 37°C with 250 r.p.m orbital shaking.

1. Additional 10 µL samples of each culture are transferred to a round-bottom microplate containing 190 µL PBS and 2 mg/mL kanamycin for flow cytometry measurements. The excess kanamycin stops bacterial protein production.

1. Repeat steps 3, 4, and 5. Steady-state conditions are not reached until about 4-10 hours of culture time. This media replacement strategy can be continued until sufficient protein expression level data has been gathered. Typically, at least 3 to 4 serial dilutions are performed for a total culture time of 24 to 36 hours.

More Details

The M9 minimal media is supplemented with 0.05 g/L leucine when usingE. coliDH10B cells, which have a leucine auxotrophic phenotype.

The M9 minimal media may be replaced with another defined media, such as MOPS minimal media or yeast synthetic defined \(SD\) media. The key requirement is that the culture's growth rate remains constant between media batches. The formulation of medias that use tryptone, yeast extract, or peptide mixtures will greatly vary between batches.

Both the spectrophotometer and flow cytometry use a gain parameter to convert photon emission counts into digitized data. It is essential that this gain parameter remain a constant throughout all experiments. Some machines offer dynamic control of the gain to maximize fluorescence sensitivity; this dynamic control should be turned off. During preliminary experiments, the gain parameter may be optimized such that: \(i\) the background fluorescence of media or white cells is 2-fold higher than detector noise; and \(ii\) the data from cell cultures expressing the highest protein expression level is 2-fold less than the machine's digital overflow value. The optimal gain parameter depends on fluorescent protein brightness and detector path length.

The spectrophotometer records cell optical density \(OD\) and fluorescence data \(FLU\) of cell culture samples, white cells, and blank media over time. For each time point, the average bulk fluorescence per cell \(FLPC\) is calculated according to:

FLPCsample=FLUsample-FLUmediaODsample-ODmedia-FLUwhite-FLUmediaODwhite-ODmedia

which subtracts the background optical density and accounts for background fluorescence from both blank media and white cell sources. This measurement is useful when the single-cell fluorescence distribution is unimodal \(single-peaked\) and when stochastic contributions to gene expression are not relevant.

Tips & Tricks

* DO NOT BREAK OUT OF MAGELLAN \*DURING\* A MEASUREMENT! THIS WILL CAUSE MAGELLAN TO CRASH AND YOUR DATA WILL NOT BE SAVED.

* Only the inner 60 wells of a 96-well microplate should be used for cell culture. During an 8 to 12 hour culture, evaporation will cause the liquid levels in the outer wells to significantly drop. The outer wells should be filled with blank media to buffer this effect.

* A cell culture has reached steady-state when: \(i\) the rate of change of FLPCsampleover time is approximately zero for a sufficiently long time; or \(ii\) the distribution of single-cell fluorescence does not significantly change between two time points. Once steady-state conditions have been reached, the recorded FLPCsampledata is time-averaged to reduce measurement noise and the fluorescence distribution's statistics are calculated.

### Tecan Measurement Parameters

Static Gains

mRFP1:225

GFP mut3b:115

Cerulean \(CFP\) :140

