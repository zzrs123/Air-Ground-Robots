# Air-Ground-Robots
## 1. 研究目标

本项目的目标是利用现有技术,整合团队成员的知识与技能， 共同实现空-地协同建图与未知环境中的自主探索， 地面机器人的复杂地形越障； 并利用地面机器人搭载的机械臂与无人机进行物资传递； 其中机械臂的抓取和运动将尝试使用视觉 抓取方式与自主规划算法进行实现。



本项目致力研发的空-地协同建图定位的搜救运载智能无人系统， 预期实现无人操作下的自主任务执行： 综合地面机器人搭载的激光雷达和空中机器人的深度相机， 以及其他多种传感器实现激光-视觉多模态的 SLAM 导航系统； 通过对 Yolov3 深度学习框架的优化与硬件部署， 结合 darknet 神经网络实现实时营救复杂环境中的被困人员和危险物品的识别与标记， 进而地面机器人结合 SLAM 建立的地图通过 Dijkstra 算法进行自主的路径规划； 通过视觉相机对待传递物体进行识别与定位， 机械臂通过 Movelt!平台与 OMPL 运动与动力学解算实现自主规划抓取传递物体。 在时间、 资源等允许的情况下， 将继续探索空中机器人在以上多传感器融合下的自主避障工作。





## 2. 研究内容

### 2.1 地面机器人的全地形移动底盘
地震、 煤矿坍塌、 建筑事故等救援现场地形复杂， 故提高地面机器人的通过能力成为本研究的一个关键。 全地形地盘拟采用主副履带设计， 利用履带式特有的强大通过能力保证再崎岖多变的地形中正常行驶。
### 2.2 多旋翼无人机稳定飞控的实现与调试
无人系统的协同配合离不开无人机的平稳巡航。 无人机虽然在机械方面的结构模型较为简单， 但难点在于飞控的实现与调试， 所以预计将有大量时间花费在飞控算法的研究与调试上， 期望实现飞控算法的鲁棒性来保证飞行巡航的稳定。
### 2.3 空-地机器人中心化与去中心化的通信系统
空-地系统有两种通信方式： 中心化与去中心化。 中心化即与同一上位机通信，通过上位机进行协同配合； 去中心化更加体现无人化的特点， 空-地两机器人直接通信与配合。 拟探索两种通信方式， 理解并实现一种或两种通信方式， 应用于本项目的智能无人系统。
### 2.4 空-地协同建图和多传感器融合的智能体路径规划
已有的激光 SLAM 和视觉 SLAM 建图方法各有利弊， 而通过无人机和无人车协同建图的方式将二者优势融合， 加以热成像、 二氧化碳传感器等多种传感器融合的信息反馈， 可以得到更加准确的实时地图， 进而方便无人系统的自主探索搜救。 此外， 由于机器人计算资源的有限以及搜救环境的复杂多变， 传统的路径规
划方法无法得到充分施展， 项目拟采用 A*启发式算法和 Dijkstra 算法实现自主导航， 结合多模态 SLAM 地图进行路径规划， 对待搜救环境进行自主探索。

### 2.5 机械臂的视觉抓取与自主规划
结合搜救的具体情况， 通过无人系统在营救方和受困人员之间传递物品成为待实现与优化的热点技术与新兴应用。 本智能无人系统拟对物体进行基于深度学习的物体识别定位， 将得到的物体姿态位置传递给地面机器人搭载的机械臂， 实现视觉抓取； 通过 movelt!编程接口实现机械臂的自主规划， 完成物品的传递。



## 3. 拟解决的关键问题

1.  地面机器人底盘的方案设计与具体实现， 为良好越障能力提供支撑；
2.  多模态 SLAM 建图算法的设计、 实现与成功部署；
3.  空-地机器人系统的自主避障与路径规划；
4.  基于深度学习的目标物体识别与定位， 实时图像回传；
5.  六自由度机械臂的自由抓取与自主运动规划；
6.  多机器人无人系统的通信模式的探索与实现；
7.  对于无人机自主避障的后续探索。



## 4. 进度安排



### 4.1 分工

* 杜高源： SLAM/Colmap建图部分，负责无人机视觉与激光、地面激光SLAM的建图工作。

* 张镇韬： 调试地面机器人以及机械臂的电控通信，维护无人机的电气元件。

* 盛家铖： 负责地面机器人和无人机的三维建模，以及后续零件装配。

* 化运涛： 负责机械臂的抓取算法设计与维护，底盘运动逻辑的设计与维护。

* 徐王锦： 无人机的视觉算法和飞控开发，以及与地面机器人的协作配合, Gazebo仿真。



### 4.2 预期计划

1. 2022.06~2022.07，通读主要的参考文献，商讨建图定位方案和机器人协作方法。
2. 2022.07~2022.09，搭建适用于室内、室外巡航的无人机，进行机械臂视觉抓取的尝试和改进，在gazebo里进行双机器人的仿真。
3. 2022.09~2022.11，进行无人机的视觉、激光导航和定位仿真和实现。
4. 2022.11~2023.1，尝试无人机建图信息和地面机器人建图信息的通信共享，进行仿真。
5. 2023.1~2023.3，进行仿真算法的实物实现，调试优化。



### 4.3 技术方案

[技术方案参考](doc/技术方案参考.md)

* 无人机建图
    - Camera DenseFusion （Realtime/Online） / colmap (Offline)
        - Stage1： 先用Colmap把流程跑通
        - Stage2： 使用SLAM + DenseFusion 实现实时三维点云重建
    - RGBD （RealSense） （不考虑）
        - http://introlab.github.io/rtabmap/
        - RealSense的作用范围太小，只有5m，可能不够
    - LiDAR （不考虑）
        - 单线激光雷达，扫描速度有些慢，需要找适合无人机的单线雷达程序
* 无人机构建的地图转化给地面机器人用
    - 三维点云地图 -> 栅格地图
    - 栅格地图给地面机器人使用
    - 无人机的栅格地图，地面机器人的栅格地图融合
* 地面机器人路径规划
* 机械手物体抓取
* 仿真
    - Gazebo仿真
    - MAVROS / PX4
    - 机械臂
* 真机实验
    - 无人机
    - 机器人

20220614-开始具体实现