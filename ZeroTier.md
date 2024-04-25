# ZeroTier使用指南

## For Windows
1. 前往[ZeroTier官网](https://www.zerotier.com/download/)下载对应版本并安装
2. 在文件资源管理器的地址栏输入`C:\ProgramData\ZeroTier\One`，替换其中的[planet文件](https://github.com/905Lab/LabDocs/blob/main/Main/planet)
3. 输入节点ID`97a9a3f27531c921`来接入内网，然后请求管理员（袁双杰，林宇嘉或李璐伯）确认

## For Linux
输入以下命令
```
curl -s https://install.zerotier.com | sudo bash
sudo zerotier-cli join 97a9a3f27531c921
service zerotier-one restart
```
然后联系管理员确认
