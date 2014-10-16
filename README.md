382-Lab-3
=========
Objectives
----------
The purpose of the lab was to become familiar with a device that used peripherals, ports, GPIO, multiplexing, polling, debouncing, and the serial peripheral interface. This was done through using the display device to create an image. The lab also provided exsposure to the logic analyzer.

Code
----
Code for this lab can be found in the Code folder.

Debugging
---------

Test Methodology / Results
----------------

Observations / Conclusions
--------------------------

Documentation
-------------


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
|       |              |              |
|       |              |              |
|       |              |              |
|       |              |              |

Writing Modes
-------------
![alt text](https://raw.githubusercontent.com/SeanGavan/382-Lab-3/master/Images/Writing.png "Writing Modes")


