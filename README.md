# Digital Dice

Produced and tested by: Joseph Chen, Nicholas Moon, Arjun Deopujari 

Configure a TM4C123 Arm Cortex-M MCU to display random numbers on an LCD peripheral based on processed data from an on-chip accelerometer.  This is called a digital dice because the MCU can be embedded within a cube and be rolled on the ground.  The accelerometer data produced from the roll will generate a random number on the screen in a smilar fashion to how rolling a dice on the ground would produce a random number (number of dots on the side facing up).

Implementation:

             - makes use of an embedded OS consisting of a thread scheduler which operates in 
             a round-robin fashion (threads can also yield their time by going to sleep). 
             
             - uses a producer thread which enqueues data to a FIFO 
             data structure (accelerometer data). 
             
             - uses a consumer threads which dequeues and performs some simple DSP filtering 
             on the data (noise removal) and then inputs the data into a pseudorandom generator 
             which then prints this new random number to the screen.
             
             - make use of one semaphore `LCDFree` which secures a thread's ownership of write 
             access to the on-board LCD peripheral screen.


