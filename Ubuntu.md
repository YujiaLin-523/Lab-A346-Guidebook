# Ubuntu

## 安装Ubuntu
实验室使用`Ubuntu 20.04 LTS`，镜像文件`ubuntu-20.04.6-desktop-amd64.iso`可以从[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/ubuntu-releases/20.04/)下载，然后用任意一台安装了Ubuntu的电脑中的启动盘创建器或者`rufus`制作启动盘。如果使用Dell电脑，则在启动时按F2进入bios，调整boot sequence，将启动盘改为第一位并保存设置，然后按照提示安装Ubuntu。注意，最好选择清理整个磁盘来安装Ubuntu，这样可以防止驱动程序等相互干扰。

## 安装常用软件

### QQ/Microsoft Edge/VS Code/Clash Verge
安装包下载地址：  
`QQ` https://im.qq.com/linuxqq/index.shtml   
`Microsoft Edge` https://www.microsoft.com/zh-cn/edge  
`VS Code` https://code.visualstudio.com/  
`Clash Verge` https://github.com/clash-verge-rev/clash-verge-rev/releases/tag/v1.5.4

.deb文件双击可以直接安装，如果不能直接安装，则尝试使用命令行安装：
```
sudo dpkg -i xxx.deb
```
Clash Verge是实验室使用的科学上网软件，安装好之后联系袁双杰导入配置文件才能使用。

### Anaconda
从[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)下载`Anaconda3-2024.02-1-Linux-x86_64.sh`文件，进入所在文件夹，右键，选择在终端打开，然后用命令行安装：
```
bash Anaconda3-2024.02-1-Linux-x86_64.sh
```