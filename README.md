# opencv_apps_demo
This package is a demo for the blob detection functionality of the opencv_apps package.

# Installation
```bash
NB: Build the workspace after checkout the blob_detection_nodelet branch of opencv_apps.
git clone --recursive https://github.com/ut-ims-robotics/opencv_apps_demo
cd src
cd opencv_apps
git checkout blob_detection_nodelet
cd ..
cd ..
catkin build
source devel/setup.bash
```
# Running Steps
```bash
The debug modes can be switched in blob_detection.launch.
in line 8, the arg debug_mode has four values: not_assigned, debug_view, ros, deploy.
"not_assigned" for turning off this argument
"debug_view" for OpenCV debug view
"ros" for rviz and rqt_reconfigure view
"deploy" for running the node with configured params loading from a yaml file
NB: Do NOT touch the arg debug_view in line 7, unless you are familiar with the opencv_apps package 
and change the value of debug_mode in line 8 to "not_assigned".
```
```bash
One suggestion of using the debug_mode is, first configure the parameters under "ros" debug mode,
and cd to opencv_apps, then save the configured parameters to a YAML file using the command:
rosparam dump config/blob_detection_config.yaml blob_detection
Then switch to the "deploy" mode.
```
## Running the blob_detection_nodelet
NB: Replace "YourTopic" in the following command to the actual image topic.
```bash
roslaunch opencv_apps blob_detection.launch image:=YourTopic
```
## Running the Find Shape demo
NB: Replace "YourTopic" in the following command to the actual image topic.
```bash
roslaunch opencv_apps blob_detection.launch image:=YourTopic
```
```bash
rosrun opencv_apps_demo find_shape.py
```
## Running the Blob Follower demo
NB: Replace "YourTopic" in the following command to the actual image topic.
```bash
roslaunch opencv_apps blob_detection.launch image:=YourTopic
```
```bash
rosrun opencv_apps_demo blob_follower.py
```
# Demo video link
https://www.youtube.com/watch?v=CJXP0X5rQqs