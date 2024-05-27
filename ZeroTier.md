# ZeroTier使用指南

## 准备
参考戈振鹏师兄的 [文章](https://zhuanlan.zhihu.com/p/383471270) 来了解虚拟局域网以及ZeroTier。

## 使用

1. 从[ZeroTier官网](https://www.zerotier.com/download/)下载ZeroTier。如果加入了其他网络，先使用以下命令退出：
    ```sh
    sudo zerotier-cli leave 3efa5cb78a3fb029
    sudo zerotier-cli leave 97a9a3f27531c921
    ```
   
2. 停止已安装服务服务：
    - **Windows**
   
        在Windows上，这是通过服务管理器完成的。打开开始菜单，然后开始输入“服务”。右键ZeroTierOneService，选择停止。
    - **Mac**
        ```sh
        sudo launchctl load /Library/LaunchDaemons/com.zerotier.one.plist
        ```
    - **Linux**
        ```sh
        sudo service zerotier-one stop
        ```

3. 从ZeroTier的工作目录删除文件`identity.public`和`identity.secret`：
    - **Windows**
        地址是  `C:\ProgramData\ZeroTier\One` 。（需要在地址栏输入文件路径才能显示）。
    - **Mac**
        地址是 `/Library/Application Support/ZeroTier/One`
    - **Linux**
        地址是 `/var/lib/zerotier-one`

4. 加入私有ZeroTier：
    - **Windows**
        1. 下载[planet](https://github.com/905Lab/LabDocs/blob/main/Main/planet)文件，并覆盖 `C:\ProgramData\ZeroTier\One` 中原有的planet文件（需要在地址栏输入文件路径才能显示）。  
        2. Win+S搜索“服务”  
           ![](https://github.com/Jonnyan404/zerotier-planet/blob/main/image/1.png)  
        3. 找到“ZeroTierOneService”，并且重启服务  
           ![](https://github.com/Jonnyan404/zerotier-planet/blob/main/image/2.png)  
        4. 使用管理员身份打开 PowerShell，执行`zerotier-cli.bat join e5ea406a0a7032d4`，出现`join ok`，随后找李璐伯后台通过。
        5. 执行`zerotier-cli.bat peers`，可以看到有一个 PLANET 和 LEAF 角色，连接方式均为 DIRECT(直连)。  
            ```sh
            200 peers
            <ztaddr>   <ver>  <role> <lat> <link> <lastTX> <lastRX> <path>
            fcbaeb9b6c 1.8.7  PLANET    52 DIRECT 16       8994     1.1.1.1/9993
            fe92971aad 1.8.7  LEAF      14 DIRECT -1       4150     2.2.2.2/9993
            PS C:\Windows\system32>
            ```
            到这里就加入网络成功了。
        
    - **Linux 客户端**
        1. 下载[planet](https://github.com/905Lab/LabDocs/blob/main/Main/planet)文件，并覆盖`/var/lib/zerotier-one`中原有的planet文件。  
        2. 使用`service zerotier-one restart`重启服务。
        3. 执行 `sudo zerotier-cli join e5ea406a0a7032d4` 加入网络，随后找李璐伯后台通过管理后台同意加入请求。
        4. 执行 `sudo zerotier-cli peers` 可以看到 PLANET 角色。
        
    - **安卓客户端配置**
        1. [ZerotierFix](https://github.com/kaaass/ZerotierFix)  
        2. [Zerotier 非官方安卓客户端发布：支持自建 Moon 节点 - V2EX](https://www.v2ex.com/t/768628)
        
    - **Mac 客户端**
        1. 下载[planet](https://github.com/905Lab/LabDocs/blob/main/Main/planet)文件，并覆盖`/Library/Application Support/ZeroTier/One`中原有的planet文件。  
        2. 使用`service zerotier-one restart`重启服务。
        3. 执行 `zerotier-cli join e5ea406a0a7032d4` 加入网络，随后找李璐伯后台通过管理后台同意加入请求。
        4. 执行 `zerotier-cli peers` 可以看到 PLANET 角色。
