# Keyboard Plate Guide

So you want to make an FR4 plate from an SVG or DXF file? Don't know where or how to start? Well you've come to the right place!

## Table of Contents

* [Setting Up](#setting-up)
* [Schematic](#schematic)
* [PCB](#pcb)
* [Production](#production)

## Setting Up

You're going to need [KiCad](https://www.kicad.org). Version 6 or higher is needed for SVG files. Download it and start the installer.

![Screenshot 1.](/assets/Screenshot-1.png "Screenshot 1.")

Click "Next >".

Uncheck "Demonstration projects".

![Screenshot 3.](/assets/Screenshot-3.png "Screenshot 3.")

Click "Next >".

![Screenshot 4.](/assets/Screenshot-4.png "Screenshot 4.")

Click "Install".

![Screenshot 5.](/assets/Screenshot-5.png "Screenshot 5.")

Click "Finish".

Start up KiCad.

![Screenshot 6.](/assets/Screenshot-6.png "Screenshot 6.")

Click "OK".

## Schematic

Create a new project (File > New Project or Ctrl+N).

![Screenshot 7.](/assets/Screenshot-7.png "Screenshot 7.")

Name the project whatever you want. For the purposes of this guide, I'll be giving it the same name as the plate file.

![Screenshot 8.](/assets/Screenshot-8.png "Screenshot 8.")

Click "Save".

Open the `.kicad_sch` file.

![Screenshot 9.](/assets/Screenshot-9.png "Screenshot 9.")

Click "OK".

You should be greeted with a blank schematic editor. Hit the A key.

![Screenshot 10.](/assets/Screenshot-10.png "Screenshot 10.")

Click "OK".

Click anywhere on the schematic, search for "GND", and select it.

![Screenshot 11.](/assets/Screenshot-11.png "Screenshot 11.")

Click "OK". Place the symbol anywhere on the schematic by left clicking (You can use the scroll wheel to zoom in and out).

Click anywhere on the schematic, search for "TestPoint", and select it.

![Screenshot 12.](/assets/Screenshot-12.png "Screenshot 12.")

Click "OK". Place the symbol so it is connected to the "GND" symbol.

![Screenshot 13.](/assets/Screenshot-13.png "Screenshot 13.")

Click on the "Select item(s)" icon.

![Screenshot 28.](/assets/Screenshot-28.png "Screenshot 28.")

Double click on "TP?" and change it to "TP1".

![Screenshot 14.](/assets/Screenshot-14.png "Screenshot 14.")

Click "OK".

Click on the "Run footprint assignment tool" icon.

![Screenshot 29.](/assets/Screenshot-29.png "Screenshot 29.")

Assign "TP1" to "TestPoint_THTPad_1.0x1.0mm_Drill0.5mm" from the "TestPoint" footprint library. Double click it to assign it.

![Screenshot 15.](/assets/Screenshot-15.png "Screenshot 15.")

Click "OK".

## PCB

Update the PCB from the Schematic (Tools > Update PCB from Schematic... or F8).

![Screenshot 16.](/assets/Screenshot-16.png "Screenshot 16.")

![Screenshot 17.](/assets/Screenshot-17.png "Screenshot 17.")

Click "Update PCB".

![Screenshot 18.](/assets/Screenshot-18.png "Screenshot 18.")

Click "Close". Place the footprint anywhere by left clicking (You can use the scroll wheel to zoom in and out).

Import graphics (File > Import > Graphics... or Ctrl+Shift+F).

![Screenshot 19.](/assets/Screenshot-19.png "Screenshot 19.")

Select the plate file, change Placement to At, and change Graphic layer to Edge.Cuts.

![Screenshot 20.](/assets/Screenshot-20.png "Screenshot 20.")

Click "OK".

Ctrl+Shift+Z then click somewhere within the plate graphic to add a filled zone. Select both the F.Cu and B.Cu layers and change the net to GND.

![Screenshot 21.](/assets/Screenshot-21.png "Screenshot 21.")

Click "OK".

Draw a small shape by clicking at each corner and finally clicking at the original point. I drew a small diamond towards the bottom left of my plate graphic.

![Screenshot 22.](/assets/Screenshot-22.png "Screenshot 22.")

Click on the "Select item(s)" icon.

![Screenshot 28.](/assets/Screenshot-28.png "Screenshot 28.")

Move the TestPoint footprint to a location within the zone.

![Screenshot 23.](/assets/Screenshot-23.png "Screenshot 23.")

## Production

Click on the "Plot" icon.

![Screenshot 2.](/assets/Screenshot-2.png "Screenshot 2.")

Specify a directory to put your gerber files into and make sure the F.Cu, B.Cu, F.Paste, B.Paste, F.SilkScreen, B.SilkScreen, F.Mask, B.Mask, and Edge.Cuts layers are selected. Check the "Use Protel filename extensions" option, and make sure the format is "4.6, unit mm".

![Screenshot 24.](/assets/Screenshot-24.png "Screenshot 24.")

Click "Plot". If you are prompted to refill zones, do so.

Click "Generate Drill Files...". Set the output directory to be the same as before, set your drill units to "Inches", and your map file format to "PostScript". Make sure "Mirror Y axis" is **unchecked**, and then click "Generate Drill File".

![Screenshot 25.](/assets/Screenshot-25.png "Screenshot 25.")

Now close the dialogs.

Put all the files you just generated into a zip file.

![Screenshot 26.](/assets/Screenshot-26.png "Screenshot 26.")

Finally, upload the gerber file to JLCPCB.

![Screenshot 27.](/assets/Screenshot-27.png "Screenshot 27.")

Consider changing the quantity and color and removing the order number.
