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

TERMINAL1
source ~/catkin_ws/devel/setup.bash
roscore

LAUNCH THE QUADCOPTER SIMULATOR

TERMINAL2
source ~/catkin_ws/devel/setup.bash
rostopic echo /quad_rotor/pose

TERMINAL3
source ~/catkin_ws/devel/setup.bash
roslaunch quad_controller hover_controller.launch
-click on "hover_controller", set target height and K values

You may observe that the quadrotor is essentially sitting on the ground, even though the hover_controller_node is running.
This is because the default target height for the controller is set to zero. In order to command it to move to a new target height at runtime, we will utilize a powerful ROS utility called dynamic_reconfigure.


