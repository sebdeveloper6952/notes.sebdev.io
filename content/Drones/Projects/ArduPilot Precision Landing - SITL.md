This project is the first one of many. The main objective is to get a good broad understanding of all the moving parts an automated drone system may have.

### End Goal
The end goal of this project is to make a physical drone land precisely on top of an Aruco marker placed on the ground.

### Components Involved
- [[ArduPilot]]
- Robotic Operating System [[ROS]]
- [[MAVLink]]
- [[ArUco Markers]]
- [[OpenCV]]

### Broad System Description
This automation is focused solely on the landing part. Takeoff and the rest of the mission is out of the scope.

This system will enter into scope when the [[Flight Modes]] `LAND` is activated.

The drone will then start descending while at the same time trying to locate a particular ArUco Marker using the camera. When it locates it, precision landing will start. The drone will then use the marker pose information to guide the rest of the landing. It should precisely land on top of the marker (accuracy should be centimeter level).

### Steps

#### 1. Camera Calibration

We created a ROS Node which purpose is to run the OpenCV camera calibration, which is a prerequisite for pose estimation.

To run this node, use the command: `ros2 run opencv_aruco_ros calib`

#### 2. Pose Estimation

The main node of the `opencv_aruco_ros` package publishes the pose of only one ArUco marker (for now).
To run: `ros2 run opencv_aruco_ros main`.
Subscribe to `/opencv_aruco_ros/pose`
#### 3. Auto Landing

First we need to set some parameters on the autopilot to enable precision landing.

We need to set the mode to GUIDED in order for the rest of commands to be accepted. Curiously enough, the format used by ArduPilot Copter differs from the MAVLink documentation. `Param1` must be set to `1` and `Param2 (CustomMode)` must be set to the flight mode.

Then we takeoff to 5 meters high.

Whenever the ArUco marker is detected, we broadcast a `LANDING_TARGET` message so the autopilot can perform a precision landing.

Then we start the landing sequence. Debug messages to track process.