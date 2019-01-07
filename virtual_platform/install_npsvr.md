## Npserver部署 {#npserver}

NPSVR默认使用端口26823与ESXI的web service通信，以达到控制和信息获取的目的。确保NPSVR所使用的端口可以被防火墙放行。

NPSVR首次运行会生成默认的配置文件，停止NPSVR后可以修改默认配置项。如端口号、日志等级等等。

NPSVR以文件方式保存规则信息和注册的虚拟化平台信息，在NPSVR重启时加载虚拟化平台的注册信息、建立连接并保持，加载备份规则并启动规则信息中标记为非停止和非完成状态的规则。

建议部署时将控制机和NPSVR的系统时间保持一致；

### Windows {#windows}

支持的Windows操作系统是Windows 64位操作系统；

双击安装程序包，出现如下界面，点击next：

![说明: 1](/assets/V7.020190107192506.png)

选中“I accept the agreement”,点击next：

![说明: 1](/assets/V7.020190107192655.png)

![说明: 2](/assets/V7.020190107192750.png)

![说明: 3](/assets/V7.020190107192830.png)

![说明: 4](/assets/V7.020190107192911.png)

![说明: 5](/assets/V7.020190107192944.png)

安装完成后确认Npsvr服务是否处于运行状态，并确认版本号信息。

**注意：**

Npsvr默认使用端口26823与esxi的web service通信，确保npsvr所使用的端口可以被防火墙放行。

### Windows卸载 {#windows-0}

开始-&gt;所有程序-&gt;NoProxy Server,双击Npsvr自带卸载程序NoProxy Server Uninstaller，也可从控制面板中找到对应软件卸载，以用NoProxy Server Uninstaller卸载程序举例，页面如下：

![说明: 1](/assets/V7.020190107193119.png)

点击Next：

![说明: 1](/assets/V7.020190107193151.png)

**注意：**

卸载Npsvr后会保留一些配置信息文件；如无保留的必要性请手动删除。

### Linux {#windows}

支持的Linux操作系统是RHEL或CENTOS 6.5 64位以上；

rpm安装

![](/assets/V7.020190107193346.png)

安装完成后检查进程及端口；

![](/assets/V7.020190107193520.png)

配置文件目录位置是/etc/npsvr/

日志文件目录位置是/var/i2data/log/

停止NPSVR的命令: service npsvr stop

启动NPSVR的命令: service npsvr start

linux卸载

打开终端或使用xshell连接到主机，使用rpm –e命令进行NPSVR的卸载：

[root@localhost /]# rpm -e rpm -e info2soft-npsvr-7.1.2-28618.x86_64

**注意：**

卸载Npsvr后会保留一些配置信息文件；如无保留的必要性请手动删除。


### 灾备机部署 {#vddk}

当虚机快照建立完成以后，灾备机与ESXI平台通信请求读取虚机的磁盘文件，备份传输到本地磁盘上，以VMDK形式保存；

因此灾备机要有足够的磁盘空间，并且加载vddk动态库，i2VP提供独立的i2node安装包集成vddk；

源机即VCenter/ESXI端无特殊配置。

* ### Windows {#vddk}

支持的Windows操作系统是Windows Server 2008 64位；

双击安装info2soft-i2node-fori2vp-7.\*.\*.\*\*\*\*\*\(x64\).exe文件；


* ### Linux {#vddk}

支持的Linux操作系统是RHEL或CENTOS 6.5 64位以上；

首先rpm安装i2node（与i2企业版的i2node相同）

![](/assets/V7.020190107194209.png)

然后rpm安装vddk plugins，注意版本对应；

![](/assets/V7.020190107194313.png)

安装完成以后，检查/usr/lib/vmware-vix-disklib/目录；


**注意：**

关于vddk版本支持的说明：

vddk6.0 plugin支持centos6.5到centos7.0；

vddk6.5 plugin支持centos6.5到centos7.2；

vddk6.0 plugin可以支持ESXI：5.1 5.5 6.0 6.5；

vddk6.5 plugin可以支持ESXI：5.5 6.0 6.5 6.7；

vddk6.5 plugin只支持El7操作系统；

vddk6.5 plugin只能应用于i2node 6.1-23885之后的版本；

如果要备份ESXI6.7版本的虚机，必须使用vddk6.5 plugin；
