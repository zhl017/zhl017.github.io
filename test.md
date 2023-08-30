# TurtleBot4 使用手冊

TurtleBot 4 是一款基於ROS2的移動機器人並以用於教學及研究為旨。TurtleBot 4 有著能夠繪製機器人周遭的地圖、自主導航、在相機上運行人工智能模組等功能。

它使用 Create 3 作為移動底座，並在上面放置已建構 TurtleBot 4 軟體的Raspberry Pi 4B。

使用 RPLIDAR A1M8 360度光達 以及 Luxonis OAK-D 鏡頭作為感測元件。

<!-- ## 資源

### 軟體

#### Ubuntu
- Ubuntu 20.04 LTS Desktop (Focal Fossa) : https://releases.ubuntu.com/20.04/
- Ubuntu 22.04 LTS Desktop (Jammy Jellyfish) : https://releases.ubuntu.com/22.04/

#### Raspberry Pi
- 映像檔燒入 Raspberry Pi Imager : https://www.raspberrypi.com/software/
- 腳位定義 Raspberry Pi Pinout : https://pinout.xyz/

#### ROS2
- 

#### TurtleBot4

#### iRobot® Create® 3

#### Luxonis

#### SLAMTEC -->

## 設定

為了能更快速的上手 TurtleBot 4，使用者需準備一台具有連接 WiFi 功能並能安裝 Ubuntu 的筆記型電腦以及能夠提供連線的 WiFi 分享器或環境。


---

### 基本設定

使用教學指令設置讓使用者PC與車子Robot間能進行基本通訊。

### 使用者 PC

#### 安裝 ROS2

建議選用與車子相對應版本的Ubuntu Desktop並且安裝ROS2。

- ROS2 Galactic

    - 作業系統要求：[Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
    - 使用腳本安裝ROS2：
    
        ```
        wget -c https://raw.githubusercontent.com/zhl017/ros_install_noetic/zhl017/ros2_install_galactic.sh && chmod +x ./ros2_install_galactic.sh && ./ros2_install_galactic.sh
        ```
    - 安裝ROS2後，安裝`turtlebot4_desktop`：
    
        ```
        sudo apt install ros-galactic-turtlebot4-desktop
        ```
- ROS2 Humble

    - 作業系統要求：[Ubuntu 22.04](https://releases.ubuntu.com/22.04/)
    - 使用腳本安裝ROS2：
    
        ```
        wget -c https://raw.githubusercontent.com/zhl017/ros_install_noetic/zhl017/ros2_install_humble.sh && chmod +x ./ros2_install_humble.sh && ./ros2_install_humble.sh
        ```
    - 安裝ROS2後，安裝`turtlebot4_desktop`：
    
        ```
        sudo apt install ros-humble-turtlebot4-desktop
        ```
        
#### 編輯環境變數文件 bashrc



---


### 機器人移動平台

設置TurtleBot 4 第一步是先開啟電源並連接到 WiFi。

#### 開啟電源

將 TurtlrBot 4 放置於充電底座上，數秒後車子 LED 指示燈會亮起並成功開機。

關於 Create3 上的按鈕與 LED 指示燈的更多詳細訊息，請參考[Create3網頁](https://iroboteducation.github.io/create3_docs/hw/face/)

#### 首次連接

當首次開啟 TurtleBot 4 時，Raspberry Pi 預設開啟(AP)模式，使用者可使用PC直接連接上它。

> **WiFi名稱：Turtlebot4**
> **WiFi密碼：Turtlebot4**

> TurtleBot 4 AP 網路預設為 5GHz，使用者需使用支援連接 5GHz WiFi 的設備才能進行連接。

#### 透過 SSH 遠端到 Raspberry Pi

成功連上 WiFi 後，透過 SSH 連接到 Raspberry Pi 上進行環境配置。在PC上開啟終端機輸入：

```
ssh ubuntu@10.42.0.1
```

> **遠端密碼：turtlebot4**

#### 將 Raspberry Pi 連接到網路

登入後，設定 Raspberry Pi 連接到 WiFi。

> 將 Raspberry Pi 連接至 5GHz 網路能獲得最佳性能。

在 SSH 視窗中輸入：
```
sudo wifi.sh -s '<WIFI_SSID>' -p '<WIFI_PASSWORD>' && sudo reboot
```

範例：

假設要連接上的 WiFi 為`example`，密碼為`123456`，需要輸入：
```
sudo wifi.sh -s example -p 123456 && sudo reboot
```

### 網路設定



## h2
