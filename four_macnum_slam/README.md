# Four Macnum Wheel Car SLAM     
该文件夹是小车SLAM(实时定位和地图构建)程序文件夹，使用Gmapping的SLAM方法。    
其中以下几个参数需注意调整：   

1. arg name="set_base_frame" default="base_footprint"    
2. arg name="set_odom_frame" default="odom"    
3. arg name="set_map_frame"  default="map"    
4. param name="maxUrange" value="12.0":雷达的最大检测距离   
5. param name="xmin" value="-5.0"：地图的X方向最小值，m   
6. param name="ymin" value="-5.0"：地图的Y方向最小值，m   
7. param name="xmax" value="5.0"：地图的X方向最大值，m   
8. param name="ymax" value="5.0"：地图的Y方向最大值，m   
9. param name="delta" value="0.05"：地图分辨率，米每像素    
10. param name="minimumScore" value="50"     
### 如果SLAM时不使用真实的雷达实时发布数据，而使用rosbag的历史数据，请在开启roscore之后立即在命令行设置"use_sim_time"参数:
```bash
rosparam set use_sim_time true
```   
