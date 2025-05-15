This repository contains ROS2 packages for the FLIR camera (formerly PointGrey). Please note that this code is tested on Ubuntu 22.04 LTS with ROS2 Humble.

To compile the driver

## Clone the repository
```
mkdir ~/ros2_ws/src
git clone https://github.com/ros-drivers/flir_camera_driver.git
cd ..
```

## To automatically install all packages that the flir_camera_driver packages depends upon, run this at the top of your workspace
```
rosdep install --from-paths src --ignore-src --rosdistro humble
```

## Build the driver and source the workspace
```
colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=RelWithDebInfo -DCMAKE_EXPORT_COMPILE_COMMANDS=ON
. install/setup.bash
```

## Run the node
```
ros2 launch spinnaker_camera_driver driver_node.launch.py camera_type:=blackfly_s serial:="'20435008'"
```
