# Introduction
This repository comprises engineering materials of the autonomous vehicle robot's model, designed for participation in the WRO Future Engineers competition in 2024. 

# Content
schemes This folder contains one or several schematic diagrams in the form of JPEG, PNG, or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect.

src This folder contains all the programming flowcharts and all programming used to participate in the WRO 2024 Future Engineers Category.

pictures-team & vehicle This folder contains photos of the team participating in the WRO, photos of the vehicle (from all sides and bottom views) and photo shown in documentation.

video This folder contains video.md file that demonstrates how the robot functions to solve both tasks.

models This folder contains the 3D design of the vehicle in .lxf and the rendered model of the vehicle.

other This folder contains other files which can be used to understand how to prepare the vehicle for the competition.

# I-Robonator Team, Malaysia
Our team, consisting of three dedicated members, meticulously manages vital aspects of the build. Here's a brief introduction to Team I-Robonator from Malaysia, along with an overview of the key electromechanical components powering our fully autonomous vehicle. Let's meet our team members:
1.	RAYMOND TING YIH WEI
2.	PUI SIN RU
3.	ADAM SYAHMI BIN MOHD SYAHRIZAL

# 1.0 Mobility Management
## 1.1 Robot Design
The autonomous vehicle robot is mainly built from the Lego 45544 Mindstorms EV3 Education Set. The build of the robot is made up of a chassis, 2 motors and 3 types of sensors.


# 2.0 Power and Sense Management
## 2.1 Power source

Revving up our robot's energy game, we've enlisted the powerhouse of Jugee Rechargeable Double A Lithium Battery, delivering an electrifying punch of 1.5V and 3000mWh. This dynamo is the driving force propelling our robotic marvel.

## 3.1 Open Challenge

The robot will run clockwise if the camera detects the orange line and the same goes to the blue line. Next, gyro sensors can make sure the robot travels in a straight line and control the robot to turn accurately. Lastly, the left and right ultrasonic sensors will assist the robot in detecting the distance between the vehicle and the wall. When the robot gets closer to the wall, the steering will do a correction to avoid hitting the wall.

## 3.2 Obstacle Challenge

The main sensor that assists the robot in this challenge is the Pixy 2 Camera. The upper part of the Pixy 2 Camera is used to detect the presence of the traffic sign. If the traffic sign is red, the steering will turn right. The same concept goes to the green traffic sign.

The bottom Pixy 2 camera will help the robot position on the map. It can make sure the robots to be in the middle on the map. It will prevent the robot from knocking the left and right wall. 


The gyro sensors still have the same function which is to make sure the robot travels in a straight line and control the robot to turn accurately.



