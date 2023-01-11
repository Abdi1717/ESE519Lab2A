# ESE519Lab2A

University of Pennsylvania, ESE 5190: Intro to Embedded Systems, Lab 2A

    Abdinajib Mohamed
            https://www.linkedin.com/in/abdinajib-mohamed-496436129/
    Tested on: MacBook Air (14-inch, 2021), macOS Monterey 12.5.1



## Setting Up Terminal

 Repo：<https://github.com/Abdi1717/ESE519Lab2-Setup>

## Reading questions for 3.2 of the Pico C SDK manual


- Why is bit-banging impractical on your laptop, despite it having a much faster processor than the RP2040?
It is very hard for the processor to switch between hard real time tasks since the processors keeps track of a lot of instructions and bit banging take up too much time.

- What are some cases where directly using the GPIO might be a better choice than using the PIO hardware?
When bit-banging is used or when LEDs are used

- How do you get data into a PIO state machine?
Moving the data from FIFO buffer to the Output shift register

- How do you get data out of a PIO state machine?
OSR shifts data out using out instructions 

- How do you program a PIO state machine?
In PIO Assembly language we write a ".PIO" file

- In the example, which low-level C SDK function is directly
responsible for telling the PIO to set the LED to a new color? How
is this function accessed from the main “application” code?
pio_sm_put_blocking() sets the LED to a new color which is accessed through put_pixel() from pattern_table[pat}.pat(NUM_PIXELS,t) which gets different patterns and picks a subroutine to run which calls put_pixel()


- What role does the pioasm “assembler” play in the example, and
how does this interact with CMake?

Pioasm changes the assembly code into binary for machine to read and by that builds Pio program. CMake calls on pioasm automatically.
---


# 3.3 
Here are the annotated ws218 files: </br>
[Annotation for 3.3 Ws218.c](https://github.com/Abdi1717/ESE519Lab2A/blob/main/Ws218.c.pdf) </br>
[Annotation for 3.3 Ws218.h](https://github.com/Abdi1717/ESE519Lab2A/blob/main/ws2812.pio.h.pdf) 
---



# 3.4

The detailed PDF is given as follows:  
[Table](https://github.com/Abdi1717/ESE519Lab2A/blob/main/3.4_RegistersList.docx) 
---


# 3.5
The detailed PDF is given as follows:  
[](https://github.com/Abdi1717/ESE519Lab2A/blob/main/3.5.pdf) 
---

# 3.6+3.7
 
 I combinned the timing diagram in 3.7 and section 3.6 into on document:
[Document](https://github.com/Abdi1717/ESE519Lab2A/blob/main/3.6%20and%203.7%20Time%20Diagram.pdf)
---

# Tools Comparison  

- What were some strengths/weaknesses of working with paper?
	- Have more space and easier for drawing diagrams
	- Hard to keep track of and gets missy 

- What were some strengths/weaknesses of working with spreadsheets?
	- Great organisation of data and make it easier to read which is one of the main strenghts.
	- Easy to copy and paste
	- Very Overwhelming.
	
- How might you approach this task using other tools available to you?
   - outsoure to online software to create timing graphs
---

# Part 4 USB + WS2812
[Code](https://github.com/Abdi1717/ESE519Lab2A/tree/main/pio)


----
# Part 4 Appendix

## Raspberry Pi Pico SDK Examples

The [Getting Started with the Raspberry Pi Pico](https://rptl.io/pico-get-started) is found to be useful for getting things up and running on my local machine.


### First  Examples

App|Description | Link to prebuilt UF2
---|---|---
[hello_usb](hello_world/usb) | The obligatory Hello World program for Pico (Output over USB version) | https://rptl.io/pico-hello-usb


### Pico Board

App|Description
---|---
[blinky](picoboard/blinky)| Blink "hello, world" in Morse code on Pico's LED
[button](picoboard/button)| Use Pico's BOOTSEL button as a regular button input, by temporarily suspending flash access.
