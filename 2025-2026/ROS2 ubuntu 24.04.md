Flash Ubuntu 24.04 on the Raspberry Pi 5 using the Raspberry Pi Imager.

Follow the installation procedure here: ROS 2 Jazzy Installation Guide.

After you finish the installation, type ros2 in the terminal. If it does not work, it’s probably because you need to source your workspace.

Install gedit using this command:

bash-
sudo apt update  
sudo apt install gedit -y
Then open .bashrc with gedit:

bash-
gedit ~/.bashrc


At the end of the file, add these lines:

source /opt/ros/jazzy/setup.bash  
source ~/ros2_ws/install/setup.bash

Save the file. Then reload it by running:
bash
source ~/.bashrc

Now type ros2 in the terminal — it should work!
