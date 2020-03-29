# DIY-Respirator
DIY design to help patients hospitalized with ARDS/covid19

# Who am I
Software developer and diy-maker. Located in Belgrade, Serbia. Please note - I am not physician, doctor nor mechanical engineer. All the knowledge I have about chemistry, biology and physics is from general education. I'm not part of the team, do not have any association with some external company, institution or government.

# Motivation
After seeing the terrible situation in the world... Italy, Spain, Europe, US... :( ... just can not sit down doing nothing. People are dying. Want to help somehow. Please take all information from this page with caution, analysis and criticism. Would like to get your feedback and suggestions to make it better.
If someone can use it as basis or to fork completely new design, all that better.

# Future use
This is just a tool to help in time of need. Please note: Do understand that no respirator alone can help without care from qualified physician and nurses from ICU! 

# Licensing
It is open-source and free. You can use it for your own commerical or non-commerical projects.

# About the project
This is general DIY diagram. It consists of off the shelf mechanical and electrical parts.

Mechanical parts:
- O2 Oxygen tank
- Ambu-Bag
- Intake and Outake valves
- Mechanical arm (hand)
- HEPA filter
- UV Lamp
- Disposable tank for bio hazardous materials

Electrical parts and controller:
- 2 x electrical solenoids (gas pressure electrical valves)
- 1 x digital gas pressure sensor
- DC servo (power rating - )
- Arduino Uno (or Mega)

# Prototype
Currently I do not have all parts to build working prototype. I do have Arduino's and some of the components; but I do miss Ambu Bag, solenoids, pressure sensors, servo (with proper power rating), different valves. It is not an issue to order those items but I do need for them to arrive (and there is also an issue of closed borders at this moment). If I can get some of this parts locally it would be great.

# After building prototype
After anyone succeds in building working prototype, we will try to find qualified physician to test the device. If they do not confirm that prototype can work or is helpful - we need to refactor this design, or abandon it for better.

# Prototype diagram

![DIYRespirator logical diagram](https://user-images.githubusercontent.com/62830023/77844882-8bad7080-71aa-11ea-90b6-caf592e37e89.png)

# Operation

Startup/Initialization/Reset:
1. Close Valve1.
2. Close Valve2.
3. Check pressure on PressureSensor1. If PressureSensor1Value >= X Goto Step 8

Main mode of operation:

4. Check AirFlow Sensor exhale breath from patient low (value <= Z)
5. Close Valve2. 
6. Open Valve1.
7. Wait until pressure on PressureSensor1 where PressureSensor1Value >= X. 
8. Arm rewinds to start position if not already there. It must be quick.
9. Close Valve1.
10. Open Valve2.
11. Start servo with Timer until timervalue >= t. Servo using arm mechanism pressures Ambu-Bag as patient inhale begins.
12. Close Valve2. Starting exhaling.

( In Parallel: Patient now exhales through Expiration path. Expiration air goes through UV Lamp and HEPA filter to Disposed tank)

13. Release Servo Arm. 
14. Repeat operation, Goto step 4.

# Timing diagram

To be done.

# Arduino sketch

To be done.
