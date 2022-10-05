# Yoonseo's Notebook

**09-27-2022**  

Decided on using servo motors for lateral movement feedback. 
Design is up for 2 options:
- Fixed pole and rotating restriction prongs
- Rotating (Side-to-Side) pole and fixed restriction prongs

Updated firmware data processing and control algorithm flowchart.

Ordered Stm32 MCU


**10-04-2022**

Decided on Micro-USB, ST-Link, FTDI Parts

Started crafting the PCB design after design review today

Design review critiques:
- Tolerance Analysis: more specific with angle precision (data value count / rotation angle degree)
- Safety: Be cautious about the servo motor torque on finger and show calculations assuring its safety.
