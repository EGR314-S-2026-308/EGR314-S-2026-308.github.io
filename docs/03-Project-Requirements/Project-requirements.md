---
title: Project Requirements
---

## **Introduction**

<!-- Write context on how features became requirements 

Written context to guide the reader on how features became requirements. (ie: The ground exploration rover will need drive and steering to move around, which requires ....  OR To collect samples, the explorer will require an arm that ....  which allows it to get the sample.)

-->
In this section as a team we will list the project requirements and then assign individuals to satisfy that requirement. We take the features proposed in our Concept Design section and turns those proposed features into requirements for the submarine, that also satisfy the requirements set out for us by the course.

Our project is currently being designed for water explorations with the intent to probe the environment in a body of water. 

This meant that we would need to isolate specific probes that would be useful in a body of water such as the light levels for vegetation growth, the temperature for general environment information and the general current information which can double as a way to read our machine's progress. Other features such as the thrusters on the side and back demonstrate a solution to the requirement of being able to move forward and reverse as well as turn. Since we can't predict the full positioning of hazards without going well over project budget the submarine needs a way to protect itself, which requires a shielding structure or more sensors.

## **Requirements**

<!--Put features list here  ~~Buoy Cable ring~~, Antenna, Test Probes, Flashlight, Optical Dome, ~~Side thrusters, Back Thrusters, Metal Cage~~ -->

<!--
Core Focus: Structural survival in high-pressure, high-risk environments.
Physical & Durability: A "structure that will withstand pressure" with "components sealed in a waterproof tube" and "corrosion-resistant" materials. It is designed for "long-term water and pressure exposure."
Safety & Logic: Includes a "leak/water detection sensor," "pressure release system," and "overheat protection." Moving parts are "covered by a barrier 4cm away" for human safety during maintenance.
Interface: Uses "high-visibility safety colors" (Red/Yellow/Blue coding) for safe physical handling and "self-diagnosis" for system integrity checks.  -->

<!-- Table that lists reqs and description as well as minimum measure to be a success, target level, feature it satisfies, and stretch/? requirement -->

| **Requirement Description** | **Feature** | **Measure of <br> Threshold** | **Target <br> Measure** | **Stretch (Y/N**) |
|-----------------------------| --------------- | ----------------- | ----------------- | :-----: |
|  The submarine requires a way to move change directions and steer forward which requires a minimum of three motors for balance. | Side thrusters and Back Thrusters |   Thrusters are able to move the submarine forward and back.   |  Thrusters are able to allow the submarine to turn and drive forward and back.     |   No   |
|  The submarine requires a way to protect the sensitive parts of the robot from bumping into obstacles.   | Metal cage | There is a solid boarder around the outside of the robot.  |  The solid shell around the robot does not warp over time and provides protection a generalized protection on all sides. | Yes |
| The submarine requires a safety measure in case of battery failure up to a certain depth.  |  Buoy ring  |  A ring offering a physical tether connection point. | A physical connection tether point with an ability to transmit data given connection. | No |
|  The submarine requires a way to send its readings back to the user from deep underwater. | Antenna | Antenna is able to send and receive the amplified signals. | Able to send and receive amplified signals  | No |
| The submarine requires a way to collect information regarding water variables like: temperature, current, and light levels | Test Probes | Probes attached to the side and send legible signals back to the HMI. | Probes have a housing that protect them from damage while not in use and allow for communication back to the HMI. | No |
| To protect a possible optical sensor/camera | Optical dome |  Keeping it water proof  | Allow for clear visuals into water |   Yes  |
| Assist camera to enhance image quality and locating the submarine | Flashlight | Provide both directed and surrounding light | Providing a clear light to clearly show what the camera sees if it's dark, while also lighting up the exterior area light for easier location of the submarine | Yes |

## **Team Responsibilities** DRAFT

| **Requirement Description** | **Assigned Team Member** |
| ----------------------------|--------------------------|
| Drive system |  Jacob             |
| Body design (safety measures)            |     Andrew / Sam B / Jacob                |
| Internal Controller/Transmiter                |     Adrian                     |
| Sensors: Tempurture/IMU/Photo resistor      |   Sam M. / Andrew / Mohammed Ali            |
| Camera                 |   Sam B. / Adrian                 |
| Human Machine Interface / U.I.               |   Sam B.                |

<!--
A table that lists the requirements, as a description, along with the minimum measure level to not be a complete failure, the target measurement, the feature this requirement satisfies, and whether it is a stretch requirement. (See the Individual data sheet template for an example.)

This table should also cover the major design-concept constraints that will affect team-member modules. Like power.
Should cover every feature of the exploration device has in the final design concept.

Should have enough requirements that every team member has a key functional requirement. Motor, sensor, wireless communication, or HMI.

A list or table that assigns the requirements to which team member.

Written context to guide the reader on how features became requirements. (ie: The ground exploration rover will need drive and steering to move around, which requires ....  OR To collect samples, the explorer will require an arm that ....  which allows it to get the sample.)


Temp - probe
Inertial Measurement Unit - attachment - also helps with knowing about currents a bit more


Sam B - UI / HMI

Jacob D - Drive system

Sensor Team
Andrew - IMU
Sam M - Temp
Mo - Light sensor

Adrian - Controller 

Desires:
Mo - HMI or whatever
Adrian - Would like a sensor
Jacob - Drive system 
Andrew - Sensor 

2 actuators, 2 sensor, 1 controller, 1 hmi
-->