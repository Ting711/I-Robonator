# Introduction
This repository comprises engineering materials of the autonomous vehicle robot's model, designed for participation in the WRO Future Engineers competition in 2024. 

# Content
schemes This folder contains one or several schematic diagrams in the form of JPEG, PNG, or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect.

src This folder contains all the programming flowcharts and all programming used to participate in the WRO 2024 Future Engineers Category.

pictures-team & vehicle This folder contains photos of the team participating in the WRO, photos of the vehicle (from all sides and bottom views) and photo shown in documentation.

video This folder contains video.md file that demonstrates how the robot functions to solve both tasks.

models This folder contains the 3D design of the vehicle in .lxf and the rendered model of the vehicle.

other This folder contains other files which can be used to understand how to prepare the vehicle for the competition.

es stability even under large loads or high speeds. The possibility of tire slippage or balancing problems is reduced by this sturdy construction.

# Team introduction
Our team, I-Robonator from Malaysia is a passionate trio dedicated to perfecting the essential components of our self-driving car. We were thrilled to introduce our committed members, Adam Syahmi Bin Mohd Syahrizal, Pui Sin Ru and Raymond Ting Yih Wei. Together, we carefully design and oversee each electronic mechanical part and ensure our self-driving vehicle runs smoothly.
 
![image](https://github.com/user-attachments/assets/b9c0bfbc-7c41-4f6c-9819-5b074d357933)
																																			
# 1.0	Mobility Management
This section covers how the vehicle movement are manged, what motors are selected, how they are selected and implemented. Besides that, a brief discussion regarding the vehicle chassis design and the mounting of all components to the vehicle chassis also provided. The discussion includes engineering principles such as speed, torque, and power.

## 1.1 Robot Design
The self-driving cars robot is built from the Lego 45544 Mindstorms EV3 Education Set. The building instruction can be found in Appendix 1. This robot is built on chassis, 2 medium motors, 3 types of sensors and 2 camera. 

![image](https://github.com/user-attachments/assets/c30c4e5b-c7c1-4eb4-8552-85d852c85711)
![image](https://github.com/user-attachments/assets/bd5e0fda-5f68-43db-bba7-7e78fecf0592)


## 1.2	 Chassis of Robot
We use a LEGO 32019+86652 tire and differential gear for our robot’s chassis. We will have a briefly discussion about the implementation of motors towards the chassis as well.

### 1.2.1 Robot’s Tire
The LEGO 32019+86652 tire combination was chosen because of its unique benefits, which make it ideal for robotics and vehicle projects requiring traction, stability, and operational efficiency. With the 32019 rim and the 86652 tire, this combination delivers a moderate size that fits medium-sized robots or cars perfectly without adding extra mass. 
By decreasing slippage, the tread pattern of the 86652 tire improves grip, which is essential for preserving stability on a variety of surfaces. It is also ideal for dynamic movements like sharp twists and abrupt accelerations because of the tight fit between the tire and rim, which guarantees stability even under large loads or high speeds. The possibility of tire slippage or balancing problems is reduced by this sturdy construction.
 

### 1.2.2 Differential gear
Two output shafts can revolve at different speeds thanks to a mechanical component called a differential gear. Robots and automobiles that need flexible steering are the primary applications for this concept. When a car rotates, the differential gear is particularly crucial since a smooth turn requires the inner and outer wheels to revolve at different speeds.
There are various benefits to designing a robot or vehicle with a differential gear. By permitting the inner and outer wheels to rotate at different speeds, it first provides smooth turning by lowering friction and the chance of skidding during turns. Besides, it makes the vehicle easier to handle, which enhances maneuverability, especially in complex or confined areas where precision steering is crucial. Third, the differential gear prolongs the life of tires and other parts by minimizing friction brought on by speed differentials between the inner and outer wheels.

 

### 1.2.3 Motor and its engineering principle
Two medium motors are used to control the robot's movement. One for steering and the other one responsible for the forward and backward motion. The steering motor enable the robot to make precise turns. The second medium motor which is the transmission motor allowed the robot to travel in both directions with controlled speed and power. This configuration gives the robot both stability and mobility, ensuring that it can operate efficiently in a range of settings. The robot performs better overall and has more precise control during dynamic activities because to the use of two separate motors for these specific tasks.


The medium motor is implemented together with different types of tooth gear. The motor starts at 260 RPM and drives a 36-tooth gear, which meshes with a smaller 28-tooth gear. This size difference makes the 28-tooth gear spin faster, reaching 335.4 RPM. Next, the 28-tooth gear connects to three even smaller 12-tooth gears, which spin 2.33 times faster than the 28-tooth gear, bringing the final speed to 781.5 RPM at the wheels. This gear system gradually increases the motor's speed, so the wheels turn quickly and efficiently at 781.5 RPM.
The Medium Motor is key to the robot’s steering system due to its light weight, speed, and precision. It enables the robot to make quick, accurate turns, helping it avoid obstacles and handle sudden changes in terrain smoothly. This motor’s precise control makes the robot more reliable for complex maneuvers.

### 1.2.4 Connection motor to the chassis
To keep the robot stable, the medium motor is placed low in the robot’s base to lower its center of gravity. This helps the robot move smoothly, reducing wobbling and rolling, especially when it turns. Lowering the center of gravity also improves balance, allowing the robot to move faster and handle rough terrain better.
A second medium motor is positioned at the front to control steering, providing precise direction changes. This motor helps the robot turn quickly and accurately, which is especially useful in tight or complex areas. Together, these motors make the robot’s movement smoother and more responsive to its surroundings.

![image](https://github.com/user-attachments/assets/f57291df-792d-4efb-bd91-a00060155e52)
![image](https://github.com/user-attachments/assets/94e73131-e2e1-46dc-a3d8-07fb37a8296b)

## 1.3 Steering
Ackermann steering relies on the engineering principle that the inner wheel needs to turn at a sharper angle than the outer wheel for smoother, low-friction turns. Linkages connect the steering arms to the wheels, adjusting their angles to reduce friction and improve efficiency. Two tie rods link the wheels' steering arms to a central pivot, ensuring precise wheel alignment as the steering wheel turns. This setup minimizes tire wear and distributes the turning load evenly. For our robot, it enables precise turning, reduces stress on parts, and supports tasks like obstacle avoidance and parking.
 
# 3.0 Obstacle Management
We control our robot using the Clev3r-Python programming language. 
 The program has two main parts which is the Open Challenge and the Obstacle Challenge. Each part has its own algorithms for handling each obstacle. 

![image](https://github.com/user-attachments/assets/7b9f4a3d-e8ec-4fe5-9b9d-31c18575078b)

## 3.1 Open Challenge
For the open challenges, we use the ultrasonic sensors to decide if the robot should move clockwise or counterclockwise. The robot will move clockwise if the right ultrasonic sensors detect a distance greater than 2000mm from the inner wall. The same goes to the left ultrasonic sensors. The ultrasonic sensors also help to measure the distance for both of the wall. It will assist the robot to adjust its steering to avoid hitting the wall as it moves closer. The gyro sensor ensures the robot stays on a straight path. 
Diagram below shows the flowchart for Open Challenge: 
 
![image](https://github.com/user-attachments/assets/7d025ffa-9709-44c3-9115-4e16fba66450)

This is the demonstration video for Open Challenge: https://www.youtube.com/watch?v=yhfqJiTPy_Y 

## 3.2 Obstacle Challenge
The Pixy 2 Camera is the primary sensor that helps the robot with this mission. The Pixy 2 camera on top is used to determine whether a traffic sign is there. The steering will turn to the right if the traffic sign is red, and to the left if the sign is green. It also use to determine the parking lot and do the parking when the robot complete 3 laps of the round. The robot will be able to determine if the traffic sign is green or red with the aid of the Pixy 2 camera behind it. The robot must make a U-turn in the third round if the final traffic sign is red. When the robot's colour sensor in front of it detects an orange line, it turns clockwise; when it detects a blue line, it turns counterclockwise. The purpose of the gyro sensors remains unchanged which is ensure that the robot moves in a straight line and to precisely control its rotation. To keep the robot from hitting the wall, both sides of the ultrasonic sensor ensure that it always maintains a safe distance between the inner and outside walls. 

Diagram below shows the flowchart for Obstacle Challenge:
![image](https://github.com/user-attachments/assets/2fdc5d5b-d88d-4237-acff-2176e7a333b9)

This is the demonstration video for Obstacle Challenge: https://www.youtube.com/watch?v=gZMsuITQNF0 



