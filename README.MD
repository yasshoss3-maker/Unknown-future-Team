# Team Unknow

## WRO Future Engineers 2026

Engineering documentation for our self-driving robot, built for the WRO Future Engineers competition.

---

## 1. Team Members
- Yassin Ahmed Hassan
- Ahmed Hossam
- Saif

---

## 2. Robot Overview
The robot is built using the LEGO Mindstorms EV3 kit, and includes:
- LEGO EV3 Brick (main controller)
- Two motors for driving the wheels
- Ultrasonic / Infrared sensor for detecting obstacles and distances
- A camera for detecting colored obstacles (red and green)Pixy2
- 4 wheels

---

## 3. Programming
Details to be added here.## 3. Programming

* **Architecture:** Programmed in Python (using EV3 Python / MicroPython) on the LEGO EV3 Brick.
* **Control Loop:** Runs a high-frequency main loop that polls ultrasonic/infrared sensors for wall distance monitoring and reads the visual sensor/camera feed for real-time obstacle tracking.
* **Steering & Steering Correction:** Implements a Proportional-Derivative (PD) control algorithm to continuously adjust steering angles based on wall distances, maintaining a consistent offset from inner/outer track boundaries.
* **Vision & Obstacle Classification:** Uses HSV color thresholding to detect green and red traffic sign pillars. The vision subsystem returns bounding boxes, allowing the robot to determine whether to pass on the left or right side of the obstacle.

---

---

## 4. Repository Structure
- `src/` - Source code for the robot's program
- `t-photos/` - Photos of the team members
- `v-photos/` - Photos of the robot from all angles
- `video/` - Link to a video of the robot in action
- `previous-iterations

---

##
## 5. Strategy

* **Wall Following & Navigation:** The robot relies on continuous distance sensing to track walls and dynamically center itself within lane boundaries, navigating straight corridors and standard corner turns smoothly.
* **Color-Based Obstacle Avoidance:**
  * **Green Obstacle:** When a green pillar is identified, the robot steers to pass on the **right** side of the block.
  * **Red Obstacle:** When a red pillar is identified, the robot steers to pass on the **left** side of the block.
* **Cornering & Emergency Recovery:** If distance sensors detect an impending wall collision or sudden track end, the robot slows down, executes a calibrated pivot turn away from the barrier, and resumes forward wall-tracking.
