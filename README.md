# VoxelMapPlus 

## Voxelmap++: Mergeable Voxel Mapping Method for Online LiDAR(-inertial) Odometry in _____
### Project Developers:
[Alfredo Gómez Mendoza](https://github.com/Freddy220103)，[Dr. Héctor Cervantes Rodríguez](https://github.com/Hector387615)
### Original VoxelMap++ Developers:
[Yuan You 游远](https://github.com/SunnysTaste)， Yifei Yuan 袁翼飞


## Introduction

We use **VoxelMapPlus** which is an expension with some new features about VoxelMap (https://github.com/hku-mars/VoxelMap) 


<div align="center">
    <img src="pics/Voxelmap++.png" width = 100% >
    <font color=#a0a0a0 size=2>The framework about VoxelMap++</font>
    <img src="pics/MergedVoxelMap.png" width = 100% >
    <font color=#a0a0a0 size=2>The Merged VoxelMap about Liren Building</font>
    <img src="pics/PointCloudMap.png" width = 100% >
    <font color=#a0a0a0 size=2>The PointCloud Map about Liren Building</font>
</div>


### VoxelMap++ in --- demonstration:
Videos are available in youtube: https://youtu.be/9DlIz0XGdv0
<div align="center">
    <a href="[[https://www.bilibili.com/video/BV16h4y1r7Cm/](https://youtu.be/9DlIz0XGdv0)](https://youtu.be/9DlIz0XGdv0)" target="_blank">
</div>


### Project Paper
Related paper available on **arxiv**:  
1. [Voxelmap++ in open -----)](https://arxiv.org/pdf/2308.02799.pdf)


## 1. Prerequisites
### 1.1. **PCL && Eigen**

PCL>= 1.8,   Follow [PCL Installation](http://www.pointclouds.org/downloads/linux.html).

Eigen>= 3.3.4, Follow [Eigen Installation](http://eigen.tuxfamily.org/index.php?title=Main_Page).

### 1.2. **livox_ros_driver**
Follow [livox_ros_driver Installation](https://github.com/Livox-SDK/livox_ros_driver).

### 1.3. **VLP-16 **
Follow [VLP16 LiDAR Installation](http://wiki.ros.org/velodyne/Tutorials/Getting%20Started%20with%20the%20Velodyne%20VLP16).


## 2. Build
Clone the repository and catkin_make:
```
    cd ~/$A_ROS_DIR$/src
    git clone https://github.com/uestc-icsp/VoxelMapPlus_Public.git
    cd ..
    catkin_make
    source devel/setup.bash
```
- Remember to source the livox_ros_driver before build (follow 1.2 **livox_ros_driver**)

## 3. Run on Dataset
### 3.1 Run on the LivoxHap Odometry dataset
Step A: Download Datasets
链接: https://pan.baidu.com/s/1-y3x7tbPbyr3LlFnH-FkWw?pwd=ICSP 提取码: ICSP 

Step B: Setup before run
Edit ``` config/velodyne.yaml ``` to set the below parameters:
1. LiDAR point cloud topic name: ``` lid_topic ```
2. IMU topic name: ``` imu_topic ```
3. If you want to show the voxel map, set ```pub_voxel_map``` to ```true```
4. If you want to show the accumulated point cloud map, set ```pub_point_cloud``` to ```true```

Step C: Run below
```
    cd ~/$VOXEL_MAP_PLUS_ROS_DIR$
    source devel/setup.bash
    roslaunch voxel_map_plus mapping_velodyne.launch
```

Step D: Play rosbag.
