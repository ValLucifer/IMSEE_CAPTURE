# IMSEE_CAPTURE
## 概述
IMSEE_CAPTURE服务于IMSEE模组，基于模组进行数据采集工作。
</br>目前软件在以下平台测试通过：
* windows10
* ubuntu1604
* ubuntu1804

</br>可选配置参数：
1. IMU帧率：100、200、500、1000
2. 图像帧率：25、50、100、200
3. 图像大小：640 × 400、1280 × 800

</br>目前 1280 × 800的图片帧率最高只支持100hz，640 × 400分辨率下，则可以达到最高200hz。
## 功能相关介绍
</br>基础功能
1. 提供左右目图片显示；
2. 提供陀螺仪、加速度计以及模组位置数据的实时显示；
1. 提供模组IMU数据的读取与保存，数据集基于EuRoC格式存储[可选项]；
2. 提供模组左右目图像单张或多张数据的读取与保存[可选项]；
4. 提供相机标定文件的获取；

## 使用指南
</br>Linux依赖：OpenCV 3.4.0或以上版本。
</br>请以sudo ./run运行程序。
</br>注：当出现错误提示为 不可执行程序时，请执行chmod +x IMSEE_CAPTURE run.sh后再次尝试。
1. 软件打开后如下:
<br>![软件主页](/data/mp.png)
2. 连接模组后的运行状态如下：
<br>![连接后的软件主页](/data/online.png)
3. IMU数据以及图片数据可以单独选择并保存到指定文件夹。
4. 采集的IMU、图片数据统一存在在名为ModuleData的文件夹下，目录结构为：
* ModuleData
    * cam0 （左目数据）
        * data (存放图像数据集)
        * data.csv (保存内容：图片时间戳 图片时间戳.png)
    * cam1  （右目数据）
        * data  （存放图像数据集）
        * data.csv  (保存内容：图片时间戳 图片时间戳.png)
    * imu0  （IMU数据）
        * data.csv (保存内容：imu #timestamp [ns],w_RS_S_x [rad s^-1],w_RS_S_y [rad s^-1],w_RS_S_z [rad s^-1],a_RS_S_x [m s^-2],a_RS_S_y [m s^-2],a_RS_S_z [m s^-2])
    * Image （单张图片保存后生成的文件夹）
        * Left (左目图片)
        * Right  (右目图片)

