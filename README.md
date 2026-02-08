# Design
## Aims
 - The primary aim of this design was to make a tool for the lab for various testing purposes, which is why there are multiple current modes for the sink.
 - The secondary aim was to experiment with image printing on PCBs and learn how to use Inkscape!

## Image vs silkscreen
 Please note, although there is silkscreen in the KiCAD project, the silkscreen was not generated as a manufacturing output, and was only used as a guide for the image in inkscape. 
 Both silkscreen *and* image printing are allowed, where silkscreen can be applied after the image printing. In hindsight, this combination could've been used.  

## Design details
The design is a simple voltage controlled current sink. The simulation for the LTSpice circuit simualtion is stored in `\sims`. 
In a nutshell, the sink is controlled by applying 0-1V into the VCONTROL input, either into the SMA connector or the right angled header. 
The `SINK_SELECTx` setting maps the 0-1V voltage input to one of either: 0-3A, 0-1A, 0-100mA, 0-10mA or 0-1mA.
_For inductive loads, please control the slew rate into the VCONTROL input, otherwise the control loop may oscillate._

## Library
The parts used in the library are stored in a different repo. For passives, the approach of using generic parts and filling them into the schematic was taken. 

# Using the PCBA

## Sink select lines
One of the `SINK_SELECTx` lines must be set, either on the board with the onboard DIP switch or by applying voltage on the external header. Please ensure all the DIP switch is all off before plugging in an external controller!

## Voltage control input
The sink is controlled b

For higher power dissipations, a fan must be mounted against the PCB to cool the DPAK transistor, which is the main dissipator of power.


# Data generation and ordering
## Kicad output data generation
Although used PCBWay, used these settings for generating the data output:
https://jlcpcb.com/help/article/how-to-generate-gerber-and-drill-files-in-kicad-9
The size came out as correct in the order page.

## Instructions for ordering
The order screenshots are shown in `\pcbway_order`.
The png files uploaded are in `\art\final_images`.
The following guide was used: 
 - https://www.pcbway.com/blog/News/Unlock_Color_PCB_Printing_with_PCBWay_0939d559.html
 - https://www.pcbway.com/project/question/KiCAD_and_Multicolor_Silkscreen.html 
