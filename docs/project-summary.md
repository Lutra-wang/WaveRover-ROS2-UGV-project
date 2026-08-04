## 担任角色
ROS2 机器人系统集成与自主导航开发负责人

## 项目简述
基于 Waveshare UGV Rover（ESP32 + Raspberry Pi 5 双控制器、6 轮 4WD、LiDAR、摄像头、机械臂），从官方 demo 跑通与问题排查入手，逐步完成 ROS2 Humble 底盘接入、SLAM 建图、自主导航、视觉识别和电脑端 LLM 控制链路验证。

## 项目要点

1. **底盘与外设 demo 打通**：基于官方 Python/Jupyter/Flask demo 验证轮子驱动、OLED、串口 JSON 控制、视频流和 Web 控件回传，排查串口路径、终端 I/O 缓冲、Python 多环境冲突等问题，为 ROS2 接入打基础。

2. **ROS2 建图与自主导航**：在 Docker 化 ROS2 Humble 环境中启动底盘、LiDAR、RViz/Gazebo，验证 Gmapping、Cartographer、RTAB-Map 建模方案，并基于二维栅格地图完成 AMCL/EMCL 定位 + TEB/DWA 局部规划的自主导航。

3. **电脑端 LLM 自然语言控制**：在电脑部署 LLM 服务，机器人 Web/ROS 节点通过 HTTP 端口发送自然语言请求，模型生成结构化 JSON/行为指令，再由 `ugv_chat_ai` 与 `behavior_ctrl` 转换为 `/cmd_vel` 或 `/goal_pose` 控制，实现“自然语言 -> 小车控制指令 -> 底盘执行”的闭环。

4. **视觉识别与自动驾驶验证**：基于 OpenCV/MediaPipe 跑通运动检测、人脸/手势/姿态识别、颜色追踪和寻线自动驾驶；寻线部分使用 HSV 筛选、腐蚀膨胀去噪和双采样线状态判断生成运动控制。

> 项目仓库：https://github.com/waveshareteam/ugv_ws
