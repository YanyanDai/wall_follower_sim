# wall follower using sc_mini LiDAR
cd ~/catkin_ws/src
git clone https://github.com/YanyanDai/sc_mini.git
git clone https://github.com/YanyanDai/wall_follower_sim.git 
git clone https://github.com/YanyanDai/racecar_simulator.git
cd ..
catkin_make
sudo cp sc_mini.rules /etc/udev/rules.d



roslaunch sc_mini start.launch
roslaunch sc_mini rviz.launch
rosrun rosserial_python serial_node.py /dev/ttyACM0   --> control the raceing car
roslaunch wall_follower wall_follower_scmini.launch
