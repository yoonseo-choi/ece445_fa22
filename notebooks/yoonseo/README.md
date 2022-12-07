# Yoonseo's Notebook

**09-27-2022: Part Selection and Firmware Brainstorming**  

Decided on using servo motors for lateral movement feedback. 
Design is up for 2 options:
- Fixed pole and rotating restriction prongs
- Rotating (Side-to-Side) pole and fixed restriction prongs

Updated firmware data processing and control algorithm flowchart.

Ordered Stm32 MCU


**10-04-2022 PCB Design Parts 1**

Decided on Micro-USB, ST-Link, FTDI Parts

Started crafting the PCB design after design review today

Design review critiques:
- Tolerance Analysis: more specific with angle precision (data value count / rotation angle degree)
- Safety: Be cautious about the servo motor torque on finger and show calculations assuring its safety.

Need to decide if we want to use CTS and RTS flow control scheme for FTDI <-> STM32 MCU


**10-08-2022: PCB Design Parts 2**

Completed the micro usb module that functions as power and usb data communication (still need to annotate fuse value)

Added basic connections for both STM32 and FT232 chip
- STM32: figure out how to use connectors on pin PA13,14 for SWD ST-Link Programmer
- FT232: Need to decide how to route other pins (i.e. NRESET, CTS, RTS, etc) and add male connectors to GND and VDD


**10-14-2022: Parts Ordering**

Completed a list of the project's BOM and started ordering the physical parts for the PCB.

Initiated a project folder on STM32 Cube IDE for the development of STM32F446RE firmware


**10-22-2022: Stm32 Development Board Testing**

Before moving everything over to our PCB, we decided to develop and test all of our firmware features on the STM32F446RE development board

Spent much time on the MCU documentation learning the specifications of the ADC channels, PWM timers, and UART communication protocols. 

Some setbacks:
- Assigning pins for each of the modules proved to be challenging since I had to make sure the pins I was using did not overlap in functionality of other relevant functionalities. 
- Setting an appropriate clock configuration (fast enough clock speed)

**10-29-2022: PCB v1.0 Order & Dev Board UART Configuration**

Made final changes to the PCB v1.0 order.

Aside from that, I continued my work on the firmware, specifically on the UART. 

All code I used for this project relied on the given HAL libraries. To see if I was sending the correct data to the PC, I configured the minicom serial monitor on my computer (running on Ubuntu) so that the HAL_UART function printed to the console.

**11-07-2022: PCB v2 Start & ADC Channel Configuration**

For our PCB v1.0, we realized a crucial mistake: not recognizing the correct operating voltage of MCU. 

Essentially, we fed 5V into a 3.3V system. Consequently, we fried our MCU, and since it took over a month for it to arrive, we decided that ordering another STM32 (from china) would be pointless given the current lead time.

To address this problem, and some other power problems, we determined using a higher power rating wall plug and a 5-3.3V Linear Converter would be new additions for our next PCB.

As for the firmware, I was able to start development for the ADC channels in order to sample the potentiometer voltage values from the finger movements. 

ADC Configuration Challenges:
- Needed to prioritize order of channel sampling and sending them to pc via uart
- Decided to utilize DMA mode for ADC for more efficient CPU cycle use

**11-12-2022: PWM Timer Configurations**

The servos we ordered required specific pwm signals to rotate certain angles.

When setting the configurations for PWM, there were many calculation to be made and setting/modifying control register to specific values.

[PWM Timer Register Configuration](image.png)

[Servo Motor Data Sheet](../../MG90S_Tower-Pro.pdf)

**11-13-2022: PCB Soldering and Firmware Algorithm Development**



