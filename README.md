### 概述
本项目基于树莓派，实现了对无人机的手势和语音简单控制。

使用硬件：
* 树莓派5
* Crazyflies 2.1
* Crazyflies PA
* SU-03T

### 手势部分
采用Google 的Mediapipe 对双手的关键点进行预测，得到关键点坐标后，再根据手势规则（根据手势的几何特性如角度，距离等设计的判断规则）得到具体的飞行指令。

### 语音部分
采用SU-03T 成品模块，模块输入语音，输出对应的串口数据到树莓派。

### 无人机控制部分
树莓派将自身摄像头判断的指令和SU-03T 传来的串口指令整合，得到最终指令，直接采用Crazyflies 官方的cflib 库调用Crazyflies PA 对无人机进行控制。
