# task1AI
Installing both ( ROS noetic + ROS2 foxy )

<br>
<br>
<br>

<img src=https://github.com/shoch77/task1AI/assets/152804738/7a0e1cd1-cf7d-40ab-81fc-b4d465ce5e28 width=10%> <br>
 ^^ The very fist step is to download (VirtualBox), <br>
    And to do that we can directly go to this link for downloading:

``` bash
https://www.virtualbox.org/wiki/Downloads
```
<br>
<br>

<img src= https://github.com/shoch77/task1AI/assets/152804738/89dda53a-26c7-49c2-8449-9a788516683f width=10%> <br>
^^ Next, we need to download (Ubuntu 20.04), <br>
   i did download the Ubuntu mate version, but it is okay if you chose any other version, <br> <br>
   and here is the link for the downloading:
```bash
https://cdimage.ubuntu.com/ubuntu-mate/releases/20.04/release/
```
   
<br>
<br>

** ROS noetic ** 
<bs>
<bs>
<bs>

<img src= https://github.com/shoch77/task1AI/assets/152804738/274d0c2e-3e60-47ff-a8ce-d315949966c9 width=20%>

# steps for Installation <br>

1 Setup your computer to accept software from packages.ros.org. <br>

  ```bash
  sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
  ```

2 Set up your keys <br>
```bash
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

3 make sure your Debian package index is up-to-date: <br>
```bash
sudo apt update
```

4 Desktop-Full Install <br>
```bash
sudo apt install ros-noetic-desktop-full
```

5 Environment setup <br> <br>
we must source this script in every bash terminal we use ROS in. <br>
```bash
source /opt/ros/noetic/setup.bash
```
It can be convenient to automatically source this script every time a new shell is launched. <br>
These commands will do that for you: <br>

!!! If you have more than one ROS distribution installed, ~/.bashrc must only source the setup.bash for the version you are currently using. <br>
```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
or <br>

```bash
echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc
```
6 Dependencies for building packages <br>
```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

--------------- <br>

^^ To start the ROS (master node) <br>
```bash
$ roscore
```
link: https://wiki.ros.org/ROS/Installation

------------------------------------------------------------- <br>

** ROS2 Foxy** 
<bs>
<bs>
<bs>

<img src=https://github.com/shoch77/task1AI/assets/152804738/85855e68-2500-43f6-b24c-a3ff065dface width=20%>

# steps for Installation <br>

first we must
