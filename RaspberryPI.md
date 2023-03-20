# 一. 树莓派启动
1. 先接HDMI , 再开启电源
2. 电源5V/3A , 保持供电稳定

# 二. 连接树莓派
1. 网线连接
   - 连线 (树莓派<->电脑)
   - 开启网络共享
   - 查找树莓派IP
   - ssh连接树莓派
   - 进入SD卡,创建ssh文件即可
2. 热点连接
   * 进入SD卡,创建文件wpa_supplicant.conf
    ```conf
    country=CN
    ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
    update_config=1
    network={
        ssid="无线网名称"
        psk="密码"
        priority=10
    }
    ```
# 三. 远程连接
1. xrdp (windows)
  `适用于Windows远程桌面连接`
  安装命令: sudo apt-get install xrdp
2. VNC (mac os)
   * 查看器
        安装于开发电脑, 下载地址: https://www.realvnc.com/en/
   * 服务器
        树莓派OS系统自带已安装, 启动命令:
        * sudo raspi-config
        * Interface options
        * VNC
      * vncserver
   * 开机自启: sudo nano /etc/init.d/vncserver
        
   * 文件传输
   * 
3. 配置静态IP地址
    1. 打开文件
      1. sudo nano /etc/dhcpcd.conf
    ```cmd
        interface wlan0
        static ip_address=ip /24
        static routers=默认网关
        static domain_name_servers=默认网关
    ```
    2. 重启


# 四. Imager烧录工具
  上官网下载OS系统与烧录工具: https://www.raspberrypi.com/software/
