---
title: Version 2.0 
tags:
- tag1
---

## **Rugged Submersible Surveyor 2.0**

As we were building and combining our modules we had discussed a few elements that we could improve and change if given a second attempt:

- More motor functionality, adding some servos and additional motors to better demonstrate control.
- Add more test points to individual pcb's to check signals.
- Add lights that default to on when the ESP powers up and when the power lines are each powered up.
- Improving the overall teams power management systems.
- Improving on our housing so that it would actually look like an mini sub, giving it more of a polished look.
- Improving the HMI controller to be able to do dual wifi communication and MQTT server connection so that someone could get our sensor data no matter the location.
- Standardizing our boards to make sure that we could easily identify possible problems.
- Giving our HUB subsystem additional buttons to test our system in case the HMI was not working or present.
- Developing a message type to adjust the sensor values and thresholds via the HMI system (Currently our system send data on a loop and also can be pinged for data if the system got interrupted).
- Developing pre-programed animations/actions from the HMI to the Motor system.
- Developing the articulated fin control from the HMI to the Motor system.
- If we get more time implementing a simple camera on to one of our systems and send that to our MQTT server/private website.
- Visualize 3d orientation on the Led screen using the IMU data.
- Implement a camera or radar for sight and see if there's a way to communicate that data back to the HMI.
- Utilize more sensor data such as speed, light intensity.
