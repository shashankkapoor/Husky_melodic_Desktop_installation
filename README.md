# Husky_melodic_Desktop_installation
Hi All, 

## Installing ROS melodic 

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
sudo apt install ros-melodic-desktop-full # recommended
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
source /opt/ros/melodic/setup.bash
```

## Dependencies for building packages

```
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
```
## python releated dependencies
```
sudo apt install python-rosdep
sudo rosdep init
rosdep update
```

## Installing Gazebo and rviz simulation
```
sudo apt-get install ros-melodic-husky-simulator
sudo apt-get install ros-melodic-husky-desktop
```

# Application opens in different terminals.

## Installing Velodyne Lidar package,driver 

```
sudo apt-get install ros-melodic-velodyne
mkdir -p ~/velodyne_ws/src && git clone https://github.com/ros-drivers/velodyne.git
rosdep install --from-paths src --ignore-src --rosdistro melodic -y
cd ~/velodyne_ws/ && catkin_make
```

# Installing VeloView for lidar (usually for see data nothing else)


# Installing Zed2 Camera
https://www.stereolabs.com/docs/ros/

http://wiki.ros.org/zed-ros-wrapper

# Installing gtsam 4.0.0-alpha2 for lego loam Slam
 ```
wget -O ~/Downloads/gtsam.zip https://github.com/borglab/gtsam/archive/4.0.0-alpha2.zip
cd ~/Downloads/ && unzip gtsam.zip -d ~/Downloads/
cd ~/Downloads/gtsam-4.0.0-alpha2/
mkdir build && cd build
cmake ..
sudo make install
```

# Installing lego loam SLAM

```
mkdir -p ~/Slam/lidar/lego_loam_ws/src
cd ~/Slam/lidar/lego_loam_ws/src
git clone https://github.com/RobustFieldAutonomyLab/LeGO-LOAM.git
cd ..
catkin_make -j1
```

#(install if lego is not running and MapOptimization Process dies.) 
```
sudo apt-get install libparmetis-dev 
```

#installing SLAM Floam 
#installing SLAM Sc-lio 
#installing SLAM lio 
#installing SLAM ORB2 
#installing SLAM ORB3  
#installing SLAM Ov2 
#installing SLAM Mulls

