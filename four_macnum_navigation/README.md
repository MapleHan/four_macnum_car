# Four Macnum Wheel Car Navigation    
该文件夹是四麦轮小车导航程序文件夹，包含了地图文件和很多参数文件，主要需要注意调整的几个参数如下：    
**局部规划器参数-dwa_local_planner_params.yaml**    
1. max_vel_x: 0.3 小车X方向(一般为前进方向)最大速度     
2. min_vel_x: -0.3 小车X方向(一般为前进方向)最小速度，如果大于等于0则小车不会后退移动     
3. max_vel_y: 0 小车Y方向(一般为左右方向)最大速度，此处可以设为大于0的值，但会导致规划器计算量加大，根据数值个人需求而定      
4. min_vel_y: 0 小车Y方向(一般为左右方向)最小速度   
5. max_vel_trans: 0.3 小车最大平移速度   
6. min_vel_trans: 0.15 小车最小平移速度    
7. max_vel_theta: 0.5 小车最大旋转速度   
8. min_vel_theta: 0.25 小车最小旋转速度    
9. acc_lim_x: 10 小车X方向极限加速度，如果加速度太小将会导致移动失败      
10. acc_lim_y: 0 小车Y方向极限加速度   
11. acc_lim_theta: 10 小车极限旋转加速度   
12. xy_goal_tolerance: 0.1 XY方向的误差(运动到距离目标点XY方向上0.1m范围内位置即认为已到达目标位置)   
13. yaw_goal_tolerance: 0.2 旋转误差(运动到距离目标方向0.2rad范围内即认为已到达目标方向)    
      
**costmap通用参数costmap_common_params.yaml**   
costmap(代价地图)，是一幅有色彩变化的地图，每一点的颜色表示小车移动到此处时可能发生碰撞的几率，即表示移动到此处需要付出的代价。    
1. footprint:  [[-0.175, -0.175], [-0.175, 0.175], [0.175, 0.175], [0.175, -0.175]]小车俯视投影的四个角点坐标    
2. observation_sources: scan 观测源   
3. scan: {sensor_frame: lidar_link, data_type: LaserScan, topic: scan, marking: true, clearing: true}这几个参数一定不能错误，
分别是观测传感器消息的frame，数据类型和话题    
     
**AMCL**    
AMCL(自适应蒙特卡洛算法)用于计算小车在地图中的位置，主要需要注意调整的几个参数如下：  
1. arg name="odom_frame_id"  default="odom"   
2. arg name="base_frame_id"  default="base_footprint"   
3. param name="laser_max_range"  value="12" 雷达最大检测距离
4. param name="odom_model_type"  value="diff" 里程计算模型，diff/omni/diff-corrected/omni-corrected   
