# Camera Calibration Guide
---
## Realsenseviewer

- Connect the realsense camera to your computer
- Open realsenseviewer and go to adnavce mode
- Check the point cloud is correctly detecting the calibration squares

## Terminator
- Launch 5 different terminals in Terminator
- Call the following commands
###### In terminal 1:
- roslaunch ur_robot_driver ur10_bringup.launch robot_ip:= #your robots ip
###### In terminal 2: 
- From directory: /opt/ros/noetic/share/ur10_moveit_config/launch
- roslaunch ur10_moveit_config moveit_planning_execution.launch
###### In terminal 3 
- From directory: /catkin_ws/src/universal_robot/universal_robot/ur10_moveit_config/launch
- roslaunch moveit_rvis.launch
###### In terminal 4
- From directory: /catkin_ws/src/universal_robot/universal_robot/ur10_moveit_config/launch
- rostopic
###### In terminal 5
- roslaunch realsense2_camera rs_camera.launch

## rviz
- Open rviz
- In the RViz "Displays" panel, click "Add"
- Then, select the "HandEyeCalibration" display type

![Alt Text](https://github.com/moveit/moveit_tutorials/blob/master/doc/hand_eye_calibration/images/add_handeye_display.png)

- Update the target parameters if needed

![Alt Text](https://github.com/moveit/moveit_tutorials/blob/master/doc/hand_eye_calibration/images/aruco_target_handeye_panel.png)
- Set the "Sensor configuration" to the one you'll be using
- The "Sensor frame" is the camera optical frame 
- The "Object frame" is the frame defined by the calibration target, which is called "handeye_target" by default
- The "End-effector frame" is the robot link rigidly attached to the camera
- The "Robot base frame" is the frame in which the calibration target is stationary

![Alt Text](https://github.com/moveit/moveit_tutorials/blob/master/doc/hand_eye_calibration/images/context_tab.png)
