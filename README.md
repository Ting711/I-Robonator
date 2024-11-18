# Introduction

This documentation covers the mobility management, power and sense management, obstacle management, and detailed sharing of our self-driving car that was precisely designed for the World Robot Olympiad (WRO) International Final 2024 Future Engineers Challenge competition.

# Content

**schemes** This folder contains one or several schematic diagrams in the form of JPEG, PNG, or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect.

**src** This folder contains all the programming flowcharts and all programming used to participate in the WRO 2024 Future Engineers Category.

**pictures-team & vehicle** This folder contains photos of the team participating in the WRO, photos of the vehicle (from all sides and bottom views) and photo shown in documentation.

**video** This folder contains video.md file that demonstrates how the robot functions to solve both tasks.

**models** This folder contains the 3D design of the vehicle in .lxf and the rendered model of the vehicle.

**other** This folder contains other files which can be used to understand how to prepare the vehicle for the competition

# I-Robonator Team, Malaysia

Our team, I-Robonator from Malaysia, is a dedicated trio with a shared passion for advancing autonomous vehicle technology. We are excited to introduce our committed members: Adam Syahmi Bin Mohd Syahrizal, Pui Sin Ru, and Raymond Ting Yih Wei. Together, we carefully design, assemble, and oversee every electronic and mechanical component, ensuring our self-driving car operates flawlessly.

![image](https://github.com/user-attachments/assets/25aaf9ce-f56e-43f8-97e3-e85b9ddcb3a4)


# 1.0 Mobility Management

This section covers how vehicle movement is managed, selection and ways to implement the motors. It also provides a brief discussion of the vehicle chassis design and the mounting of all components to the chassis. The discussion includes engineering principles such as speed, torque, and power.

## 1.1 Self-Driving Car Design

The self-driving car is constructed using the Lego 45544 Mindstorms EV3 Education Set. It features a car’s chassis, powered by two medium motors, and equipped with three sensors and two cameras. 

![image](https://github.com/user-attachments/assets/e8cf8dc2-d895-4efa-8001-030984a1e314)

Additionally, a custom 3D-printed component has been installed to enhance its functionality. For detailed building instructions and the view of the 3D printing process, kindly refer to the QR code provided below.

![image](https://github.com/user-attachments/assets/9b3a4420-dd02-4e37-bc74-48b551f096ab)

## 1.2 Chassis of Self-Driving Car

Our self-driving car's chassis uses a LEGO 32019+86652 tyre and differential gear. We will also briefly discuss how motors are implemented on the chassis.

### 1.21 Self-Driving Car’s Tyre

The LEGO 32019+86652 tyre combination was chosen because of its unique benefits, which make it ideal for robotics and vehicle projects requiring traction, stability, and operational efficiency. With the 32019 rims and the 86652 tyre, this combination delivers a moderate size that fits medium-sized robots or cars perfectly without adding extra mass. 

By decreasing slippage, the tread pattern of the 86652 tyre improves grip, which is essential for preserving stability on a variety of surfaces. It is also ideal for dynamic movements like sharp twists and abrupt accelerations because of the tight fit between the tyre and rim, which guarantees stability even under large loads or high speeds. The possibility of tyre slippage or balancing problems is reduced by this sturdy construction.

![image](https://github.com/user-attachments/assets/b7fbae36-53ff-404c-95d7-1de1a89d1d9f)

### 1.2.2 Differential Gear

Two output shafts can revolve at different speeds thanks to a mechanical component called a differential gear. Robots and automobiles that need flexible steering are the primary applications for this concept. When a car rotates, the differential gear is particularly crucial since a smooth turn requires the inner and outer wheels to revolve at different speeds.

There are various benefits to designing a robot or vehicle with a differential gear. Permitting the inner and outer wheels to rotate at different speeds first provides smooth turning by lowering friction and the chance of skidding during turns. Besides, it makes the vehicle easier to handle, which enhances manoeuvrability, especially in complex or confined areas where precision steering is crucial. Third, the differential gear prolongs the life of tyres and other parts by minimising friction brought on by speed differentials between the inner and outer wheels.

![image](https://github.com/user-attachments/assets/d27a207a-de89-4c4f-a9eb-560722ab069a)

### 1.2.3 Selection of Motor and Its Engineering Principle

Two medium motors are used to control the robot's movement. One is for steering, and the other one is responsible for the forward and backward motion. The steering motor enables the robot to make precise turns. The second medium motor, which is the transmission motor, allowed the robot to travel in both directions with controlled speed and power. This configuration gives the robot both stability and mobility, ensuring that it can operate efficiently in a range of settings. The robot performs better overall and has more precise control during dynamic activities because of the use of two separate motors for these specific tasks.

![image](https://github.com/user-attachments/assets/30410677-d4da-4f6a-87fa-b295a9c4a565)

Motors implementation and its engineering principle

![image](https://github.com/user-attachments/assets/b7ddd2c3-bfe6-4ec7-a7e8-b7b08d34a82d)

The medium motor is implemented together with different types of tooth gear. The motor starts at 260 RPM and drives a 36-tooth gear, which meshes with a smaller 28-tooth gear. This size difference makes the 28-tooth gear spin faster, reaching 335.4 RPM. Next, the 28-tooth gear connects to three even smaller 12-tooth gears, which spin 2.33 times faster than the 28-tooth gear, bringing the final speed to 781.5 RPM at the wheels. This gear system gradually increases the motor's speed, so the wheels turn quickly and efficiently at 781.5 RPM.

The medium motor is key to the robot’s steering system due to its lightweight, speed, and precision. It enables the robot to make quick, accurate turns, helping it avoid obstacles and handle sudden changes in terrain smoothly. This motor’s precise control makes the robot more reliable for complex maneuvres.

### 1.2.4 Connection of Motor To The Chassis

To keep the robot stable, the medium motor is placed low in the robot’s base to lower its center of gravity. This helps the robot move smoothly, reducing wobbling and rolling, especially when it turns. Lowering the center of gravity also improves balance, allowing the robot to move faster and handle rough terrain better.

A second medium motor is positioned at the front to control steering, providing precise direction changes. This motor helps the robot turn quickly and accurately, which is especially useful in tight or complex areas. Together, these motors make the robot’s movement smoother and more responsive to its surroundings.

![image](https://github.com/user-attachments/assets/ba3a0ffc-a692-4296-8c5d-7adf16eb673a)

## 1.3 Steering

Ackermann steering relies on the engineering principle that the inner wheel needs to turn at a sharper angle than the outer wheel for smoother, low-friction turns. Linkages connect the steering arms to the wheels, adjusting their angles to reduce friction and improve efficiency. Two tie rods link the wheels' steering arms to a central pivot, ensuring precise wheel alignment as the steering wheel turns. This setup minimizes tyre wear and distributes the turning load evenly. For our robot, it enables precise turning, reduces stress on parts, and supports tasks like obstacle avoidance and parking.

![image](https://github.com/user-attachments/assets/c757db2e-8dca-4f2a-9727-9096a71d1350)

# 2.0 Power and Sense Management

The power and sensor management section explains the vehicle's power source and the sensors it uses to help the vehicle navigate different challenges. It also covers the reason certain sensors were chosen and how they work with the vehicle, including their power usage. The section also comes with a wiring diagram and the Build Of Material (BOM) that shows all the components and how they are professionally wired together.

## 2.1 Power Source

We use the Jugee Rechargeable AA Lithium Battery, which provides 1.5V and 3000mWh of power, to drive our robot forward.

![image](https://github.com/user-attachments/assets/d972e6bb-2fd4-428e-ac55-c12d66c2376a)


## 2.2 Sensor

The robot is equipped with several sensors such as the Pixy 2 camera, an EV3 sensor multiplexer, a color sensor, a gyro sensor and an ultrasonic sensor. These sensors work together to help the robot navigate smartly. The figure below shows the connection between the sensors to the EV3 Hub.

**Front view of the robot**

![image](https://github.com/user-attachments/assets/568f6a12-a09f-4efc-a025-019986a15722)


**Back view of the robot**

![image](https://github.com/user-attachments/assets/eee6404f-9885-4ca8-abfe-e3aa9ccd5326)


**(i) Pixy 2 Camera**

The Pixy 2 camera helps the robot recognize traffic signs and parking lots, allowing it to move more efficiently and make real-time decisions based on its environment.

The figure below shows the details look of the Pixy 2 Camera:

![image](https://github.com/user-attachments/assets/2672c420-754f-4b49-9237-3aa88f177eb5)

In camera systems, the tilt angle, focal length, and field of view are crucial for effective monitoring. A 60-degree tilt offers a balanced coverage area, clear images, and reduces distractions. The Focal Length and Field of View Principle explain that a shorter focal length gives a wider view, which, combined with tilt, expands coverage, especially in large areas. The 60-degree tilt extends the camera’s coverage and minimizes blind spots, ensuring no critical areas are overlooked. This allows the robot to track the traffic signs and the parking lot more precisely.

![image](https://github.com/user-attachments/assets/07a6ea6d-d81a-451a-bc0e-5a71a6e24d21)

![image](https://github.com/user-attachments/assets/c5289491-9bed-4bca-a2f1-f507df5713f5)

Since there was no Lego part to secure the Pixy 2 Camera, we designed a custom 3D-printed component to firmly lock it in place on the robot. This ensures the camera stays steady during movement, preventing shaking that could affect pixel capture and improving accuracy in detecting obstacles.

![image](https://github.com/user-attachments/assets/7e4d6e23-ec61-4f2c-bc23-ced7696b0a69)

**(ii) Color Sensor**

A color sensor in LEGO Mindstorms robots detects and distinguishes colors by emitting light and measuring how much is reflected. This helps the robot stay on the correct path and follow directions. Sometimes the color sensor misreads due to external light interference, so we wrap it in black tape to shield it from light, ensuring more accurate color readings.

![image](https://github.com/user-attachments/assets/b738730a-8e1b-4425-85bf-2171124524a9)

**(iii) Gyro Sensor**

The gyro sensor helps the robot stay stable and move accurately by tracking its rotation. It detects changes in direction, ensuring the robot moves straight and turns precisely. The gyro sensor often has data errors, causing fluctuations. In order to fix this, we will hard reset it before each robot operation.

![image](https://github.com/user-attachments/assets/e5817616-e9e2-46b1-8f6a-2197a00a0c80)

**(iv) Ultrasonic sensor**

The ultrasonic sensor was chosen to help the robot to measure distances and detect the wall. It uses sound waves to find the wall and calculates the distance based on how long the sound takes to return. This prevents the robot from knocking into the wall.

![image](https://github.com/user-attachments/assets/c807ed4c-3eeb-4126-addd-dcc1800895f4)

**(v) EV3 Sensor Multiplexer**

The EV3 Sensor Multiplexer allows us to connect more sensors to an EV3 brick, which normally has a limited number of sensor ports. It expands the robot's ability to interact with its environment by letting multiple sensors use a single port.
 
![image](https://github.com/user-attachments/assets/dd1a77dc-e817-435e-8f54-bfc0678f32e6)

## 2.2 Build of Materials

The table below is the build of materials (BOM) that is needed for the vehicle robot. The Build of Materials (BOM) is the summary list of all the parts that are needed to build our self-driving car. The table shows the names, quantities, and details of each item, helping to ensure all necessary parts are available and correctly used during assembly. It also helps track and organize the parts for the robot or car’s construction.

![image](https://github.com/user-attachments/assets/4e9cfc41-4373-4390-a531-2a869d31f6d9)

![image](https://github.com/user-attachments/assets/55358e2e-7736-44cb-b83b-ab1843582f9c)

![image](https://github.com/user-attachments/assets/05c461e2-31ca-42b9-94df-e1db5dc401b0)

![image](https://github.com/user-attachments/assets/4467b56b-83b7-4f35-882e-9576d1b4dd8a)

![image](https://github.com/user-attachments/assets/fbad9195-4b49-43a0-9bfd-25d99535a4c3)


## 2.3 Wiring Diagram

The following wiring diagram illustrates the connection of motors and sensors on our self-driving car, accommodating both the open challenge and obstacle challenge configurations.

**(i) Open Challenge**

![image](https://github.com/user-attachments/assets/cbbad0e8-723a-4e55-af62-1ec0d47184e6)

**(ii) Obstacles Challenge**

![image](https://github.com/user-attachments/assets/11195ba5-4962-498f-ad27-a5565a666c2c)

# 3.0  Obstacle Management

In this section, we will discuss how our self-driving car successfully tackled both the Open Challenge and the Obstacle Challenge. Additionally, a video explaining the robot’s structure and showcasing demonstrations of each challenge is accessible via the QR code below

![image](https://github.com/user-attachments/assets/dd0c2cc8-410e-4832-bc1c-cecb0451b299)


We programmed our robot using the Clev3r-Python programming language for precise and efficient operation. 

![image](https://github.com/user-attachments/assets/939b30f0-e76e-4c20-a334-34b74149eeaa)


## 3.1 Open Challenge

For the open challenges, we use the ultrasonic sensors to decide if the robot should move clockwise or counterclockwise. The robot will move clockwise if the right ultrasonic sensors detect a distance greater than 2000mm from the inner wall. The same goes for the left ultrasonic sensors. The ultrasonic sensors also help to measure the distance for both of the walls. It will assist the robot to adjust its steering to avoid hitting the wall as it moves closer. The gyro sensor ensures the robot stays on a straight path. 

Diagram below shows the flowchart for Open Challenge: 

![image](https://github.com/user-attachments/assets/db5b84f3-8734-414b-9161-3b59baaef006)

The following is an explanation of the code that is used in the robot for Open Challenge:

![image](https://github.com/user-attachments/assets/cc8b1dea-631e-4a87-b89b-82177471547d)

**1. Getting direction:** The robot uses the gyro sensor to get the heading direction.


![image](https://github.com/user-attachments/assets/4ad1d04a-308b-452e-9325-28f53fa1e38a)

**2. Turning:** The robot uses the ultrasonic sensor to make sure the timing of turning. It will turn with the 90 degrees when the value between the ultrasonic and inner wall exceeds 800mm.


![image](https://github.com/user-attachments/assets/111e590a-172d-43b6-978f-9a229f86c901)

**3. Avoid Walls:** The robot uses an ultrasonic sensor to maintain the distance between the walls and the robots. When the robot gets closer to the inner wall, the steering will do a correction to avoid hitting the wall.


## 3.2 Obstacle Challenge

The Pixy 2 Camera is the primary sensor that helps the robot with this mission. The Pixy 2 camera on top is used to determine the presence of traffic sign. The steering will turn to the right if the traffic sign is red, and to the left if the sign is green. It is also used to determine the parking lot and do the parking when the robot completes 3 laps of the round. The robot will be able to determine if the traffic sign is green or red with the aid of the Pixy 2 camera behind it. The robot must make a U-turn in the third round if the final traffic sign is red. The color sensor is used to detect the blue and orange line on the map. When the robot's color sensor in front of it detects an orange line, it turns clockwise; when it detects a blue line, it turns counterclockwise. The purpose of the gyro sensors remains unchanged which is to ensure that the robot moves in a straight line and to precisely control its rotation. To keep the robot from hitting the wall, both sides of the ultrasonic sensor ensure that it always maintains a safe distance between the inner and outside walls. 

Diagram below shows the flowchart for the Obstacle Challenge:

![image](https://github.com/user-attachments/assets/46eb6e34-c5ec-4b24-98ca-5f2fba47ce83)

The following are explanations of the code that is used in the robot for the Obstacle Challenge.

![image](https://github.com/user-attachments/assets/ac937e74-1f65-4323-844c-ca23dc7b4801)

**1. Getting direction and turning:** The robot uses the color sensor to check the line on the game field. When the first line it detects is orange, then it will run clockwise and the same concept for the counterclockwise. Then, it uses the gyro sensor to get the heading direction.


![image](https://github.com/user-attachments/assets/cfc59518-3f76-48dd-bf7b-5d697291dc1b)

**2. Avoid Walls:** The robot uses both sides of the ultrasonic sensor to check the value of the distance between the robot. The value is used to prevent the robot from colliding with the wall.


![image](https://github.com/user-attachments/assets/4c42ff2c-086d-4709-a41f-8e891b54b668)

**3.Avoid traffic sign:** The robot uses the upper Pixy 2 Camera to detect the presence of the traffic sign. The steering will turn to the right side if the traffic sign is red, and to the left side if the sign is green. 


![image](https://github.com/user-attachments/assets/7f1ddcb8-a54e-45b1-be5b-9869a6554b01)

**4. U-turn:** The robot uses the behind Pixy 2 Camera to detect the traffic sign placed behind of the robot. If the traffic sign is red, then it will do a U-turn when the third laps start.


![image](https://github.com/user-attachments/assets/11a15a77-3578-4cc3-bf84-98bd59884a04)

**5. Parking:** The robot uses the upper Pixy 2 Camera to detect the magenta parking lot and do parking after completing 3 laps for the challenge.


# 4.0 Engineering Factors

This section provides detailed information on the 3D-printed parts and all third-party components installed in our self-driving car.

We encountered several challenges in completing both the Open Challenge and the Obstacle Challenge. For example, we lacked a suitable LEGO part to secure the Pixy 2 Camera on the robot, and we faced a shortage of sensor ports needed for our design. To address these issues and enhance our robot’s performance, we incorporated third-party components alongside the EV3 45544 Mindstorms Education Set. The diagram below shows the summary of the third-party components that we used to solve the problems.

![image](https://github.com/user-attachments/assets/eeeea0d2-cba5-49b2-ab78-113918cec55c)

A 3D printed Pixy 2 Camera Holder is used to solve the issue of securing the Pixy 2 Camera It provides the stability to keep the camera securely in place, even during movement or sharp turns. This stability enables the Pixy 2 Camera to continuously capture essential data for detecting and interpreting traffic signs without disruption, improving the robot’s responsiveness to environmental cues and enhancing its performance in both the Open Challenge and the Obstacle Challenge.

To expand our sensor capabilities, we implemented the EV3 Sensor Multiplexer, allowing us to operate six sensors simultaneously. This setup includes two ultrasonic sensors for obstacle detection and distance measurement, two Pixy 2 cameras for visual tracking and traffic sign recognition, a gyro sensor for precise orientation, and a color sensor for surface recognition and line-following. By integrating all six sensors, our robot can process a diverse range of environmental data in real-time, enabling more accurate and efficient navigation and obstacle response. This configuration maximizes the robot’s adaptability and capability to handle complex tasks, making it versatile and responsive in various scenarios.

Lastly, with the Pixy 2 Camera, the robot can accurately detect and interpret traffic signs on the field, allowing it to make informed decisions for obstacle avoidance based on real-time data.

**5.0 Improvements and enhancements**

**(i) Installment of crash barrier onto the self-driving car**

The wheels tended to hit walls during traffic sign avoidance, so we added crash barriers on both sides of the robot. These barriers act as buffers, redirecting the robot away from obstacles before the tires make contact. This reduces friction and prevents the robot from getting stuck, allowing it to move smoothly without obstruction.

![image](https://github.com/user-attachments/assets/194a4eac-ea00-4f85-b058-7a3d4842d2d3)

**(ii) Hard reset of gyro sensor**

The gyro sensor frequently encounters data errors, causing value fluctuations. A hard reset of the gyro sensor is performed before each operation to eliminate data errors and prevent value fluctuations, ensuring accurate readings throughout the program.

![image](https://github.com/user-attachments/assets/b36ed89c-8699-473e-92b0-a293b9adce81)

**(iii) Ensuring continuous operation of ultrasonic sensor**

The ultrasonic sensor has an issue where it may turn off unexpectedly during operation without any warning. To address this, we've developed a program that automatically sets the robot's motor speed to zero whenever the ultrasonic sensor detects a value of zero. This precaution effectively halts the robot's movement until the sensor resumes normal operation, reducing any risks associated with the sensor failure. Once the ultrasonic sensor begins detecting values again, the robot will return to its normal speed, ensuring smooth and uninterrupted movement.

![image](https://github.com/user-attachments/assets/ffbd3f06-73e1-4db0-867e-46b0846cb9b0)

**Credits**

We would like to express our sincere gratitude to LEGO Education for their invaluable support and commitment in providing us with a high-quality LEGO EV3 set. Appreciation to the team sponsors from Ministry of Education Innovation and Talent Development Sarawak (MEITD);  SOP Foundation and YB Dato Sri Lee Kim Shin.


