### OS Setup

Install ubuntu 22 server (arm64). This works the best with ROS.

### OpenCV

Cross compile on separate machine and install. [This tutorial](https://docs.opencv.org/4.10.0/d3/dd9/tutorial_crosscompile_with_multiarch.html) actually worked.

### ROS2

Follow the [installation instructions](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html) for ROS2 Humble.
Install `ros-humble-ros-base` & `ros-dev-tools`
Always remember to `source /opt/ros/humble/setup.bash`

### Mavros

Follow the `apt` commands in the [official instructions](https://github.com/mavlink/mavros/tree/master/mavros#installation).