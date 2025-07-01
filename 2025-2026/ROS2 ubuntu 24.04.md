✅ ROS 2 Jazzy Installation Steps for Raspberry Pi 5
1️⃣ Flash Ubuntu 24.04 LTS

Use the Raspberry Pi Imager to flash Ubuntu 24.04 LTS onto your Raspberry Pi 5’s microSD card.

2️⃣ Install ROS 2 Jazzy

Boot up your Pi and open a terminal.

Follow the official ROS 2 Jazzy installation guide here:
👉 Install ROS 2 Jazzy on Ubuntu

3️⃣ Check if ROS 2 works

After installation, type:

"ros2"
If you see command not found, it means you still need to source your ROS environment.

4️⃣ Install gedit to edit .bashrc

Install gedit with:

bash
Copy
Edit
sudo apt update
sudo apt install gedit -y
5️⃣ Add ROS source commands to .bashrc

Open your .bashrc file:

bash
Copy
Edit
gedit ~/.bashrc
At the end of the file, add:

bash
Copy
Edit
source /opt/ros/jazzy/setup.bash
source ~/ros2_ws/install/setup.bash
⚠️ Note: Only include the ~/ros2_ws line if you have already created and built a workspace. Otherwise, add it later.

Save the file and close gedit.

6️⃣ Reload .bashrc and verify

Reload your terminal settings:

bash
Copy
Edit
source ~/.bashrc
Now test ROS 2:

bash
Copy
Edit
ros2
It should now work without any errors.

✅ You’re ready to use ROS 2 Jazzy on your Raspberry Pi 5!
