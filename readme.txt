DOWNLOAD quad simulator
https://github.com/udacity/RoboND-Controls-Lab/releases


mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
cd ~/catkin_ws/src
git clone https://github.com/caudaz/robotND1-proj4_Quadrotor_PID
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src --rosdistro=kinetic -y

cd ~/catkin_ws/src/robotND1-proj4_Quadrotor_PID/quad_controller/cfg
chmod 755 *
cd ~/catkin_ws/src/robotND1-proj4_Quadrotor_PID/quad_controller/scripts
chmod 755 *

cd ~/catkin_ws
catkin_make
source ~/catkin_ws/devel/setup.bash

UPDATED quad_controller/src/quad_controller/pid_controller.py (USING LESSONS CODE)

########### HOVER CONTROLLER and DYNAMIC RECONFIGURE #############################

1-TERMINAL
source ~/catkin_ws/devel/setup.bash
roscore

2-LAUNCH THE QUADCOPTER SIMULATOR
"INPUT OFF" TO CONTROL WITH ROS

2-TERMINAL
source ~/catkin_ws/devel/setup.bash
rostopic echo /quad_rotor/pose

3-TERMINAL
source ~/catkin_ws/devel/setup.bash
roslaunch quad_controller hover_controller.launch
-click on "hover_controller", set target height and K values

################  TUNING #########################

4-TERMINAL
source ~/catkin_ws/devel/setup.bash
rosrun quad_controller hover_zn_tuner_node
              OR    
rosrun quad_controller hover_twiddle_tuner_node


