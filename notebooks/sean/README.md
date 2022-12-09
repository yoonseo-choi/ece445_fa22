# Sean's Notebook

## 09-22-2022

Had a meeting with the team to brainstorm about what part to use for lateral movement feedback.
2 part options we came up with:
- servo motors (we haven't figured out how we will modulate motors)
- magnetic friction brakes (haven't found a part that would fit fot our design)

Did some research on the parts I've mentioned and found a few different products

## 09-27-2022

Our team decided on using servo motors for lateral movement feedback after more research and having some talk with TA.

We ordered STM32 MCU

## 10-03-2022

We finalized our parts list and started ordering them.

Yoonseo and I started working on the schematics.

## 10-08-2022

Finished the schematic.

![version1_schematic](https://user-images.githubusercontent.com/114099808/206584786-2a872f7a-00e4-431a-9909-e143a15c6d6b.png)

## 10-09-2022

Started working on PCB design.

Problems:
- so many tangled connections near the MCU (since pins of the MCU are facing all four ways)
- the PCB still has too much unused space

Solutions & things I learned:
- to untangle all unconnected ones, I decided to use some vias (solved the congestion near the MCU
- I found out that wires can go through parts when there is no connecting pins. previously I thought I have to go around all parts which led me to have so much empty space left

## 10-14-2022

Finished designing PCB

![version1_pcb](https://user-images.githubusercontent.com/114099808/206587523-940ab804-4452-412a-9ac1-84e84f19ba07.png)

I learned how to order our PCB from PCBWAY website and how to generate gerbers.

## 10-16-2022

My teammates and I realilzed that some of the components were not available to order and also we had to use a different micro-USB for our second round PCBway order

## 10-28-2022

Aaron picked up our version1 PCB.

![pcb_1](https://user-images.githubusercontent.com/114099808/206590080-861cc847-8a5e-4f95-ac74-153bd7e1468f.png)

## 11-01-2022

Assembled PCB

## 11-17-2022

We realized that we need a linear voltage regulator to drop down 5V to 3.3V for MCU

## 11-18-2022

Added a linear voltage regulator to our PCB.

Also added a few more testpads and some pin holes for later use.

Connection for the barrel jack is also added to the design for our 5V power input.

Version2 PCB done.

![version2_pcb](https://user-images.githubusercontent.com/114099808/206591726-9f84e7fa-a92d-49be-a949-6b5e36bed305.png)
