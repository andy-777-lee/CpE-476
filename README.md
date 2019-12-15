# CpE-476
-Chae Hyeok Lee
-Kwon Seung Cho
-Ki Ju Kim

Task 1: Description of the Mobile Robot, include documentation and reference to datasheets, images, assembly instructions, etc. 

Our Mobile Robot is the Light Duty Robot (Option 2). The robot based on Pololu A-star32U4 and from Pololu. 
We followed instruction of construction from their website. Link to the hardware that we got can be found below.

Romi Chassis Kit : https://www.pololu.com/product/3501/resources
Romi 32U4 Control Board: https://www.pololu.com/product/3544/resources
Romi Encoder Pair Kit: https://www.pololu.com/product/3542
Rpi3: https://www.raspberrypi.org/products/raspberry-pi-3-model-b/


Task 2: Motor and Encoder Testing - In this task, the team will perform basic tests for the motor (proper forward, backward, right and left motion), and encoder operations.

For the Task 2, we make use of Romi32U4 Arduino library to assist us interface with the motors.
For the for the Encoder operation, we used Encoder example. After several experiments we realized that right side of motor needed to be set more higher speed in order to move straight line. The speeds are (100,103).
The other motions ( backward, left, right motion) are the same way with straight line test.


Task 3: Wheel Calibration (fix systematic errors)- The goal of this task will be to move your robot using built-in commands for a distance of 2 meters. 
Determine the trim values of the motor such that the robot travels in a straight line.

Our general motor spec is below. 
Gear ratio 120:1
150rpm (4.5v  200)
Wheel diameter is 70mm ( circumference=7*3.14 = 21.98cm ) 
From the specs of our rover, to go to the 2 meters, the wheels have to spin 9 times.
Using those specs, we set valid value to go 2 meters. Additionally, one our wheels waved a lot. This required addition time and testing to troubleshooting. 



Task 4: Unidirectional & Bidirectional Square Path Experiment - In this task the robot, follows a path comprising of four straight line segments and four pure rotations about the robot's center point, at the corners of the square. The robot's end position visualizes the dead-reckoning error. To do this, first we did the Romi to go straight for a meter. Next we used opposite speed to each motorA and motorB. So the Romi can turn 90 degrees perfectly. We did this for 4 times and the Romi made the square path.

Task 5: PID Control - Implement PID control to offset unknown tracking errors. Use supplied K values. You can modify them later. We used the PID example code to do this task. PID Control can do accurate and optimized automatic control. 

Task 6: Dead Reckoning - Using the of motor encoder values, calculate the robot's position and pose for the motor basic test. The robot’s position and pose changed during it runs.

Task7: https://github.com/pololu/romi-32u4-arduino-library. Based on this, the acceleration and gyro values can be found in rviz.
https://github.com/ftPeter/RomiPi/tree/master/Arduino/Romi-RPi-I2CSlave we can check it using this code. odometry.ino


Task9: RPI3 used ROS+OpenCV Raspbian Lite Image - http://bit.ly/2P5OIgd Used, using PuTTY to connect to the host PC.

RPI4 used https://drive.google.com/open?id=1x9sBT5NIcZZSm1t_fGI7lC7NXaa3P7-_ Ubunto18.04 ROS (Kinetic)On RPI4, ROS (Kinetic) was not installed properly on Ubunto18.04, which made it impossible to install the OPENCV Package properly.

We tested the OPENCV using RPI3 and found that the OPENCV was installed normally.


Task10: https://github.com/ftPeter/RomiPi/tree/master/Arduino/Romi-NoRpi-Debug First of all, we added and uploaded the file from the Romi-NoRpi-Debug.ino code, and tried to check it out using therosrun teleop-twist_keyboard teleop_twist_keyboard.py but failed.

