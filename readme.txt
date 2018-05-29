mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
cd ~/catkin_ws/src
git clone https://github.com/caudaz/robotND1-proj4_Quadrotor_PID
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src --rosdistro=kinetic -y
cd ~/catkin_ws
catkin_make
source ~/catkin_ws/devel/setup.bash

cd ~/catkin_ws/src/robotND1-proj4_Quadrotor_PID/quad_controller/cfg
chmod 755 *

DOWNLOAD quad simulator
https://github.com/udacity/RoboND-Controls-Lab/releases

