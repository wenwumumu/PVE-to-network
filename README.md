# PVE疑难问题:新增或者减少NVME\网卡\显卡等pcie设备导致WBE管理界面失联或者BOOM，一键解决，而且之后再怎么添加和减少设备都会自动更正网卡位置，更正直通网卡序号，妈妈再也不用担心我折腾了。

**服用方法：**
**先在原设备（折腾前），复制代码到shell终端 回车运行**
如：
![image](https://github.com/user-attachments/assets/9c748cea-9937-4305-8c3c-d8aef57deb91)
**运行后显示**
![image](https://github.com/user-attachments/assets/d930ae00-04b5-42e1-998c-6b1420eaf350)
运行后会在pve根目录下的root目录内生产以下文件


wen      主角程序


xxwenwu  当前lspci获取的pcie信息


wenmu    获取conf配置内直通的通道等信息    此文件重要   是更正pcie直通通道序列的关键


wmac     当前管理口的mac信息             重要重要              是更正管理口的关键

![image](https://github.com/user-attachments/assets/cffe6f15-5a0c-4ea3-8df8-1b3900524c6d)


程序自动备份管理网口配置文件 /etc/network/interfaces 为/etc/network/interfaces.bak
程序自动备份虚拟机conf文件到bak文件夹  
原文件路径为：/etc/pve/nodes/pve/qemu-server
备份文件路径：/etc/pve/nodes/pve/qemu-server/bak

**国内版**

wget -q -O wen 'http://oyuo.cn:5244/d/wen?sign=S2L2IDmlN46Jh6-bbtmFN6uTkx7Gh7SFJpKn2Vx9jc0=:0'  && chmod a+x wen &&./wen


**国外版**

wget -q -O wen 'https://github.com/wenwumumu/PVE-to-network/raw/main/wen' &&chmod a+x wen && ./wen
