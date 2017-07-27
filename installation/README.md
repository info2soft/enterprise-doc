# 安装和卸载

1、硬件配置要求

最低配置:CPU2核4线程内存2G

推荐配置:CPU2核4线程内存4G

最佳配置:CPU4核内存4G,或以上

2、一般情况下工作机模块、灾备机模块和控制机模块分别独立部署在不同的服务器上，但也可任意部署在同一台或者两台机器上。比如，在服务器A上安装工作机模块，在服务器B上安装控制机模块和灾备机模块。

针对上述的三个模块，i2提供两类软件安装包：info2soft-i2node-6.0-*安装包和info2soft-ctrlcenter-6.0-*安装包，其中info2soft-i2node-6.0-*安装包包含工作机模块和灾备机模块，info2soft-ctrlcenter-6.0-*安装包包含控制机模块。

目前i2node支持安装平台支持列表如下：

| i2node安装包名称 | 操作系统版本 |
| --- | --- |
| info2soft-i2node-6.0-xxxx.exe | Windows Server 2003 (R2) 32位 |
|  | Windows Server 2008 32位 |
|  | Windows Server 2012 32位 |
|  | Windows XP SP3 32位 |
|  | Windows 7 32位 |
|  | Windows 8 32位 |
|  | Windows 10 32位 |
| info2soft-i2node-6.0-xxxx(x64).exe | Windows Server 2003 (R2) 64位 |
|  | Windows Server 2008 (R2) 64位 |
|  | Windows Server 2012 (R2) 64位 |
|  | Windows 7 64位 |
|  | Windows 8 64位 |
|  | Windows 10 64位 |
| info2soft-i2node-6.0-xxxx.el4.i386.rpm | RHEL4系列（EL、Elsmp）32位 |
| info2soft-i2node-6.0-xxxx.el4.x86_64.rpm | RHEL4系列（EL、Elsmp）64位 |
| info2soft-i2node-6.0-xxxx.el5.i386.rpm | RHEL5、CentOS5系列(el5、el5PAE、el5xen) 32位 |
| info2soft-i2node-6.0-xxxx.el5.x86_64.rpm | RHEL5、CentOS5系列(el5、el5PAE、el5xen) 64位 |
| info2soft-i2node-6.0-xxxx.el6.i686.rpm | RHEL6、CentOS6系列 32位 |
| info2soft-i2node-6.0-xxxx.el6.x86_64.rpm | RHEL6、CentOS6系列 64位 |
| info2soft-i2node-6.0-xxxx.sles.10sp1.x86_64.rpm | SUSE Linux Enterprise Server 10 SP1 64位 |
| info2soft-i2node-6.0-xxxx.sles.10sp2.x86_64.rpm | SUSE Linux Enterprise Server 10 SP2 64位 |
| info2soft-i2node-6.0-xxxx.sles.11sp1.x86_64.rpm | SUSE Linux Enterprise Server 11 SP1 64位 |
| info2soft-i2node-6.0-xxxx.sles.11sp2.x86_64.rpm | SUSE Linux Enterprise Server 11 SP2 64位 |
| info2soft-i2node-6.0-xxxx.sles.11sp3.x86_64.rpm | SUSE Linux Enterprise Server 11 SP3 64位 |
| info2soft-i2node-6.0-xxxx.ubuntu.12.04.2.x86_64.deb | Ubuntu 12.04.2 64位 |
| info2soft-i2node-6.0-xxxx.debian.7.1.x86_64.deb | Debian 7.1 64位 |
| info2soft-i2node-6.0-xxxx.debian.7.4.x86_64.deb | Debian 7.4 64位 |

I2控制机安装平台支持的是： RHEL5和6系列、CentOS的5和6系列，以及Windows XP SP3、Windows Server 2003&amp;2008和Windows 7以上系统，支持32位和64位平台，如以版本6.0-xxxx为例，对应安装包参考如下列表：

| ctrlcenter安装包名称 | 操作系统版本 |
| --- | --- |
| info2soft-ctrlcenter-6.0-xxxx.exe | Windows XP SP3、Windows 7、 |
| info2soft-ctrlcenter-6.0-xxxx.el5.i386.rpm | RHEL5、CentOS5以上系列 32位 |
| info2soft-ctrlcenter-6.0-xxxx.el5.x86_64.rpm | RHEL5、CentOS5以上系列 64位 |
| info2soft-ctrlcenter-6.0-xxxx.el6.i686.rpm | RHEL6、CentOS6以上系列 32位 |
| info2soft-ctrlcenter-6.0-xxxx.el6.x86_64.rpm | RHEL6、CentOS6以上系列 64位 |

注意：所有模块的安装必须在Linux/Unix root用户、Windows administrator用户或具有相关超级权限的用户下进行。

 * [节点(i2Node)安装](node_install.md)
 * [控制机(i2CtrlCenter)安装](ctrl_install.md)
 * [软件卸载](soft_uninstall.md)

