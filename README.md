# rm_backup
此项目为rm_version 主干代码备份

代码讲解
[君录屏](https://www.bilibili.com/video/BV1oX4y167RP/?buvid=YC409CC4F420B2184DAAB1AB05066B6C403D&is_story_h5=false&mid=aMylOvu8G9n93cRXN2jkVg%3D%3D&p=1&plat_id=116&share_from=ugc&share_medium=iphone&share_plat=ios&share_session_id=8FD2BE68-23DD-4FAC-9390-B25679A80F86&share_source=QQ&share_tag=s_i&timestamp=1681105429&unique_k=08YiJg7&up_id=14510518&vd_source=626d577a2bd051f791761b175758c1b2)

电控端适配
[模型适配整车状态最优估计器自瞄的电控部分](https://github.com/CodeAlanqian/SolveTrajectory)


[docker使用配合的网址](https://studio.foxglove.dev/)

[项目开发地址，请去此处开发](https://github.com/Github-YoMi-Ya/rm_developing_version)

## 食用方法

注意：新版本需要插上串口才能正常启动否则会进入报错自动关闭

### 启动全部节点launch文件

无硬件：ros2 launch rm_vision_bringup no_hardware.launch.py

有硬件：ros2 launch rm_vision_bringup vision_bringup.launch.py

### 开启串口
sudo chmod 777 /dev/ttyUSB0

### 启动可视化：
ros2 launch foxglove_bridge foxglove_bridge_launch.xml port:=8765

### 浏览器打开可视化  
https://studio.foxglove.dev/

### 查看相机帧率
ros2 topic hz /camera_info

### 关闭所有节点
ros2 node killall

## 项目结构
### rm_auto_aim
rm自瞄代码
具体请参考rm_auto_aim中的readme文档

### rm_gimbal_description
RoboMaster 视觉自瞄所需的 URDF 参考

### rm_serial_driver
实现部分与电控通讯功能
具体参考文件中的readme

### rm_vision
Docker部署文件
项目启动脚本

### ros2_hik_camera
海康工业相机ros2的包
