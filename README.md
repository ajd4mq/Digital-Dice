# Digital Dice
Configure a TM4C123 Arm Cortex-M MCU to display random numbers on an LCD peripheral based on processed data from an on-chip accelerometer.
Implementation makes use of an embedded OS consisting of a thread scheduler which operates in a round-robin fashion (threads can also yield their time by going to sleep).
