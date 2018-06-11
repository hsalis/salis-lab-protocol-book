# Genetic QPix2 Colony Picker

`PROTOCOL DUMP PLEASE FORMAT`

## How to set up machines & cabling

_Notes:_

1. Read the manual!
2. Make sure that nothing \(eg. deep well plates, plate, cover etc\) is blocking the movement of the actuator.
3. Make sure that you use the correct head \(96-pin or 384-pin\)
4. Only use Genetix plate and Genetix compatible well plates/petri dish. \(Genetix Tray = 240 x 240 x 20 mm square-shaped QTray Bioassay Tray for agar \(Catalog no. : X6023\) ; ~ 8.5 times bigger than normal petri dish\)
5. Place the \(deep\) well plates on the proper position! Even a slight mistake will cause damage to the pin.
6. Always remove the head and clean it after use!
7. Do not leave the machine working on its own. Use slow motion mode if you are not sure of the movement of the actuator and always position your hand on the STOP button to prepare for any unpredicted circumstances. Otherwise, open the door of the machine will also stop the actuator.

\(A\) Turning on the machine

1. First turn on the huge switch on the side of the machine and press the "reset" button on the front panel. Release the EMERGENCY STOP button if it is not released. \(\*broken right now leave alone\*\)
2. Turn on the compressor below the machine \(it may take some time for the air to be detected by the machine or for the compressor to warm up\)
3. Turn on the computer. \(Password : caporsap\)
4. Double click on the Qpix program that you would like to use \(Picking mode or replicating mode\). This will turn the machine \(actuator\) on.
5. Add 70% or 80% ethanol to the washing bath.

![](https://lh4.googleusercontent.com/14MO5xVDfpzijL5qwM6tpYWZcCFDs8kINWGEHKM4cfjx0MoslS87OCMy20NDLGTjrwLFTU1-ehyKp6w4WtXFJs3uHetkq-fkcPqrSkshnelvBi2zcdZ9XhWcey3TJD9QrXx96sxj)

Figure. Make sure that all the lights are on for the first three button \(red rectangle\) and the lights are off from the “RESET” button \(green rectangle\). Make sure that the STOP button is released.

\(B\) Using the picking mode

1. Change the head to 96-pin or 384-pin head.
2. Do a pin firing test for all pins.
3. Using the test tray \(with paper and styrofoam instead of agar\), align the camera to pin A1. Adjust the z position of the pin to make sure that the pin reaches the appropriate height and makes a hole on the paper. But the pin should not go too deep that it hits the bottom of the tray. Adjust the x and y position if the camera does not align to the hole made by pin A1.
4. Remove the test tray. Turn on UV for 20 min.
5. Prepare your deep well plate. Add 500ul of media to each well for Beckman 96-Well Deep Well Plate.
6. When UV is off, place your agar tray and deep well plate into the machine at appropriate position. DO NOT put deep well plate at position 1-10!! Start at position 11 for deep well plate. Make sure that all the covers for agar tray and deep well plate are removed and placed out of the way of the actuator
7. Then, you can run your colony picking scripts.

\(Extra\) Agar plates

1. Use only Genetix plates\(trays\) as stated above. They are reusable by washing with 80% ethanol and drying in the oven \(use paper towels or supporting structure to prevent direct contact between the plate and the oven, which will melt the plate\). Do not autoclave!
2. Add 200 ml of agar to each plate. Make the plate only on very flat surface!
3. Calculate the appropriate amount of cells require. Tips: If your cells are distributed properly on a normal petri dish \(diameter = 9cm\), plate around 8.5 times the amount \(at same OD600 and dilution factor\) on the Genetix plate.

### Setup

1. Fill wash bath with 70% EtOH. Make sure all brushes are fully submerged in EtOH. See photo. Do not spill EtOH anywhere else. If you do, immediately wipe up. The imagining panel window is sensitive.

### Changing the head

If pins on the head are bent. You might need to swap the head out & replace with the alternate head with fixed pins.

1. Click “Change Head”
2. QPixII will move head to front left corner. Do not press “OK” on the computer.
3. Unscrew knob on far left of the head.
4. Remove head. Be careful! It’s heavy. Don’t let it drop. Use two hands!
5. Replace pins \(follow protocol\)
6. Place head back on. Press “OK”. Head should move to back right corner of machine.

### Operation

1. Select your container source \(BIOASSAY TRAY if you are using a Qtray; PETRI DISH HOLDER n if you are sampling from petri dishes\)
2. Ignore the “Barcodes” button
3. Select agar volume = 200 mL
4. Colour normally select which option you want \(generally “white” if working with bacteria\)
5. Destination \(these parameters are flexible\)
6. 1. Container = DEST PLATE HOLDER \(1x5\)
   2. Plate: BECKMAN 96 DEEP WELL PLATE \(or what you are using; very important\). If you are using IPTG
   3. Max Plate = \(select\)
   4. Replicates \(don’t recommend\) = 1 pick & n many deep wells \(70% is lost in first well\)
   5. Dips to inoculate = 5 \(default\)
   6. Inoculate After: \(how many picks?\) 96 is fine for E. coli. Yeast/B.subtilis are sticky & evaporate faster, go for lower. \(\*Daniel will play with this and figure out optimized settings for B. subtilis\)
   7. Well Offset: \(to skip wells\)
   8. Stir: You don’t need to stir for E. coli
7. Head
8. 1. 96 PIN PICKING HEAD
   2. Pin Order - you can select a default picking order, or customize your own!
9. Sterilizing
10. 1. Leave parameters alone. Pins are hot! Make sure to wait 10 seconds after sterilization. Bath cycles = Seconds in dryer = Wait after drying = 10 sec.
11. Additional Options
12. 1. “Leave Light Table on” - turn off when you are setting up. Turn on when you run.

### Pin Firing Test

After a crash, you might need to run a test to make sure things are working fine.

### Test Image

A preliminary check to see how good the QPixII will pick from your plate.

### Running Picking Mode

1. Add Qtray to image pane window. Make sure to screw down
2. Add Deep Well plates \(see photo\)
3. You can run “Full” or “Partial”; Partial if only want to pick from region from the Qtray. Highlight region to pick \(or all\). Don’t pick @ edge. This software is dumb. Might think that the edge is a colony.
4. Align the camera? Usually don’t need to. You can according to the “Alignment Protocol” section.
5. Prepare Picking Script, “YES”. The machine will take an imagine of the region.
6. Display Image Data, “YES”. Let’s look at it!
7. You can select the different regions in the box to the bottom right.
8. “Colors” will show you the legend of what each color corresponds to on the image.
9. 1. Blue = discarded because of roundness
10. “Tools”, you can adjust the parameters for colony selection. Any time you changes these parameters, you need click “Re-Process”
11. Right click on colony, you can select colonies manually. You can “Deselect Colony” as well if there is something wrong with it, or if it’s not a colony. You need to step through this. If your plate is too crowded, this step is going to take forever! Save yourself time and plate good Qtrays.
12. Use position number 11 for DEEP WELL PLATE. Make sure to check setting in software.
13. When you run it, you can check the “Slow Motion” option. This is good to do for the first time. Hover over the EMERGENCY STOP button and be ready to press it if anything goes wrong! It will be obvious if the machine is crashing \(i.e. loud!\).

## Plating a Qtray

Plasmid transformation: calculate 500-1,000 colonies on Qtray is a good density objective.

Plate on petri dishes before, estimate efficiency. Or plate multiple Qtrays with varying 10-fold dilutions.

Add beads; spread beads around.

Other things to do for clean up:

1. Pour springs and pins into beaker
2. Add DI water
3. Just a little soap
4. Shake
5. Sonicator would be good otherwise manually shake
6. Rinse
7. Let dry
8. UV then 10 min

\*\*\* TO DO LIST FOR THE COLONY PICKER \*\*\*

Send QSOFT 1 & 2 to IMAN

Order list:

* Wash bath x2
* Brushes x2
* petri dish holder x1 \(4 plate\)
* Q-trays
* springs/pins for head
* Screw tip pins for B. subtilis/yeast growth
* Beckman 96-well deep well plate \(1 mL\)

\*RUN COLONY PICKER IN SLOW MODE IF YOU AREN’T USING 1 mL PLATES

