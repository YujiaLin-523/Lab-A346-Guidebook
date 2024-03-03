# NVIDIA显卡驱动

## 关闭nouveau
执行以下语句关闭nouveau
```
sudo gedit /etc/modprobe.d/blacklist.conf
```
在末尾添加：
```
blacklist nouveau
options nouveau modeset=0
```
执行以下语句进行更新并重启：
```
sudo update-initramfs -u
sudo reboot
```

## 下载驱动文件并安装
在[NVIDIA官网](https://www.nvidia.cn/geforce/drivers/)下载对应的驱动，将目标文件夹在终端中打开，执行以下语句进行安装：
```
sudo IGNORE_PREEMPT_RT_PRESENCE=1 bash ./*.run
```
完成后执行以下语句进行验证：
```
nvidia-smi
```