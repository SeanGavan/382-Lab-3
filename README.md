382-Lab-3
=========
Objectives
----------
The purpose of the lab was to become familiar with a device that used peripherals, ports, GPIO, multiplexing, polling, debouncing, and the serial peripheral interface. This was done through using the display device to create an image. The lab also provided exsposure to the logic analyzer.

Code
----
Code for this lab can be found in the Code folder (lab3.asm).

Debugging
---------
Pressing the button would no longer write to display. Reverted back to original code to fix.
Changing 0xE7 to 0xFF made one complete column of pixels, but only 1 column. Added a loop for multiple column writes.

Test Methodology / Results
----------------
Altered different values to see what was actually writing to the display. Changed the 0xE7 to 0xFF to create a full column  
of pixels.
Created a loop within the code that would write the full column 8 times. This loop uses a counter register to do so.

Observations / Conclusions
--------------------------
After receiving tips from Capt. Trimble, I was able to figure out how to make the box by using a jump loop and adjusting what  
was being stored as the data to write onto the display.
Documentation
-------------
Captain Trimble told me how to change the 0xE7 data into 0xFF to create a full 8 pixel column. She also told me that  
a loop would be effective in creating 7 additional columns to create the entire 8x8 pixel box.

Answers to Lab Questions
------------------------
| Line  | R12   | R13   | Purpose  |
| :---: | :---: | :---: | :------: |
| 66    | #NOKIA_DATA | #0xE7 | Write the data stored onto the given location |
| 276   | #NOKIA_CMD | remove upper nibble, mask with 0xB0 | Select a row of 4-bits |
| 288   | #NOKIA_CMD | copy top of stack, shift right 4 bits, remove upper nibble, mask with #0x10 | 2 sets of 4-bits |
| 294   | #0x00      | copy top of stack, remove upper nibble | Copy the top of the stack |

| Line  | Command/Data | 8-bit packet |
| :---: | :----------: | :----------: |
|   204    |       1      |      10101010        |
|   214    |       0      |      00001111       |
|   201    |       1      |      11110000       |
|   186    |       1      |      00001111        |

Writing Modes
-------------
![alt text](https://raw.githubusercontent.com/SeanGavan/382-Lab-3/master/Images/Writing.png "Writing Modes")


