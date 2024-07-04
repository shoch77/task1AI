# task1AI
Installing both ( ROS noetic + ROS2 foxy )

<br>
<br>
<br>

### Step 1: Download and Install VirtualBox <br>

<img src=https://github.com/shoch77/task1AI/assets/152804738/7a0e1cd1-cf7d-40ab-81fc-b4d465ce5e28 width=15%> 
<br>
The very fist step is to Download and Install VirtualBox, And to do that: <br>

- go to this link: https://www.virtualbox.org/wiki/Downloads
- Download the version for your operating system (Windows, macOS, Linux)
<br>

### Step 2: Downloading Ubuntu 20.04 <br>

<img src=https://github.com/shoch77/task1AI/assets/152804738/89dda53a-26c7-49c2-8449-9a788516683f width=15%> 
<br>

i did download the Ubuntu mate version, but it is okay if you choose any other version <br>

## ^^ The Requirements for Ubuntu Mate
<br>

<img src=https://github.com/shoch77/task1AI/assets/152804738/32de523f-7a03-4d3b-b6da-4d4b03a59354 width=80%>
<br><br>

 to download it: <br> 

- go to this link: https://cdimage.ubuntu.com/ubuntu-mate/releases/20.04/release/
- Download the Ubuntu 20.04 mate ISO file 
<br>


### Step 3: Create a New Virtual Machine in VirtualBox <br> 

1:: Open VirtualBox and click on New to create a new virtual machine. <br>
2:: Name your virtual machine and select Linux as the type and Ubuntu (64-bit) as the version. <br>
3:: Allocate memory (RAM) to your virtual machine. <br>
4:: Create a virtual hard disk. Select Create a virtual hard disk now and click Create. <br>
5:: Choose VDI (VirtualBox Disk Image) as the hard disk file type and click Next. <br>
6:: Choose Dynamically allocated and click Next. <br>
7:: Set the size of the virtual hard disk (20GB for mate) and click Create. <br>


### Step 4: Install ROS on Ubuntu 20.04
<br>

** ROS noetic ** 
<bs>
<bs>
<bs>

<img src= https://github.com/shoch77/task1AI/assets/152804738/274d0c2e-3e60-47ff-a8ce-d315949966c9 width=20%>

## steps for Installation <br>
- Once Ubuntu 20.04 is installed and running in virtual machine, we can proceed with installing ROS1:
 <br> <br>

1:: Setup your computer to accept software from packages.ros.org <br>

  ```bash
  sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
  ```

2:: Set up your keys <br>
we set up the keys needed to authenticate packages.ros.org:
```bash
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

3:: Update package index <br>
make sure the Debian package index is up-to-date <br>
```bash
sudo apt update
```

4:: Install ROS 1 <br>
You have a choice between a full desktop install and a minimal install (just command-line tools). <br>
For the desktop install (recommended for beginners):
```bash
sudo apt install ros-noetic-desktop-full
```
5:: Initialize rosdep <br>
Before using ROS, initialize rosdep:
```bash
sudo rosdep init
rosdep update
```

6:: Environment setup <br> <br>
we must source this script in every bash terminal we use ROS in. <br>
```bash
source /opt/ros/noetic/setup.bash
```
It can be convenient to automatically source this script every time a new shell is launched, <br>
These commands will help: <br>

```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
or <br>

```bash
echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc
```
7:: Dependencies for building packages <br>
```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

--------------- <br>

^^ To see if the ros has installed corecctrlly, we test the ROS's (master node), <br>
   and to do that: 
```bash
$ roscore
```
<br>

<img src = https://github.com/shoch77/task1AI/assets/152804738/63c65463-0301-4c05-b182-d1241dc0b83c width=50%>

<br> <br> 
----
link: https://wiki.ros.org/ROS/Installation 
----

-------------------------------------------------------------
<br>

** ROS2 Foxy** 
<bs>
<bs>
<bs>

<img src=https://github.com/shoch77/task1AI/assets/152804738/85855e68-2500-43f6-b24c-a3ff065dface width=20%>

# steps for Installation <br> 

 <br> <br>

1:: Set locale

```bash
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
```
2:: Setup Sources

```bash
sudo apt install software-properties-common
sudo add-apt-repository universe
```
```bash
sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```
3:: Install ROS 2 packages

```bash
sudo apt update
```
```bash
sudo apt upgrade
```
```bash
sudo apt install ros-foxy-desktop python3-argcomplete
```
```bash
sudo apt install ros-foxy-ros-base python3-argcomplete
```
```bash
sudo apt install ros-dev-tools
```

4:: Environment setup

```bash
source /opt/ros/foxy/setup.bash
```
<br>
------ <br> 

since there is no master node in Ros2, <br>
we need to do some examples to see if its working or not <br>

^^ Trying some examples  

:: In one terminal, source the setup file and then run a C++ talker 
<br>
<br>
<img src=https://github.com/shoch77/task1AI/assets/152804738/18198212-516f-4a14-b31b-449ddc8e934a width=50%> 
<br>
<br>
::In another terminal source the setup file and then run a Python listener 
<br>
<br>
<img src=https://github.com/shoch77/task1AI/assets/152804738/8aa73e46-7c69-4bb3-8707-8d85b922be18 width=50%>
<br>
<br>

----
link: https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html
----
