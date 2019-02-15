# 安装和卸载

1、硬件配置要求

```
最低配置:CPU2核4线程内存2G

推荐配置:CPU2核4线程内存4G

最佳配置:CPU4核内存4G,或以上

日志、流量图等信息发送到控制机时，数据库读取大部分是通过时间过滤的，请确保部署软件前将所有机器系统时间保持一致，避免由于系统问题导致在软件使用的过程中出现不和谐的问题
设置好系统时间后，尽量不要修改系统时间，如CDP等是通过时间点记录数据操作等，修改可能导致数据不可用
```

2、一般情况下工作机模块、灾备机模块和控制机模块分别独立部署在不同的服务器上，但也可任意部署在同一台或者两台机器上。比如，在服务器A上安装工作机模块，在服务器B上安装控制机模块和灾备机模块。

   针对上述的三个模块，i2提供两类软件安装包：info2soft-i2node-6.1-\*安装包和info2soft-ctrlcenter-6.1-\*安装包，其中info2soft-i2node-6.1-\*安装包包含工作机模块和灾备机模块，info2soft-ctrlcenter-6.1-\*安装包包含控制机模块。

目前i2node支持安装平台支持列表如下：

| i2node安装包名称 | 操作系统版本 |
| --- | --- |
| info2soft-i2node-6.x-xxxx.exe | Windows Server 2003 \(R2\) 32位 |
|  | Windows Server 2008 32位 |
|  | Windows Server 2012 32位 |
|  | Windows XP SP3 32位 |
|  | Windows 7 32位 |
|  | Windows 8 32位 |
|  | Windows 10 32位 |
| info2soft-i2node-6.x-xxxx\(x64\).exe | Windows Server 2003 \(R2\) 64位 |
|  | Windows Server 2008 \(R2\) 64位 |
|  | Windows Server 2012 \(R2\) 64位 |
|  | Windows 7 64位 |
|  | Windows 8 64位 |
|  | Windows 10 64位 |
| info2soft-i2node-6.x-xxxx.el4.i386.rpm | RHEL4系列（EL、Elsmp）32位 |
| info2soft-i2node-6.x-xxxx.el4.x86\_64.rpm | RHEL4系列（EL、Elsmp）64位 |
| info2soft-i2node-6.x-xxxx.el5.i386.rpm | RHEL5、CentOS5系列 32位 |
| info2soft-i2node-6.x-xxxx.el5.x86\_64.rpm | RHEL5、CentOS5系列 64位 |
| info2soft-i2node-6.x-xxxx.el6.i686.rpm | RHEL6、CentOS6系列 32位 |
| info2soft-i2node-6.x-xxxx.el6.x86\_64.rpm | RHEL6、CentOS6系列 64位 |
| info2soft-i2node-6.x-xxxxx.el7.x86\_64.rpm | CentOS7系列64位 |
| info2soft-i2node-6.x-xxxx.sles.10sp1.x86\_64.rpm | SUSE Linux Enterprise Server 10 SP1 64位 |
| info2soft-i2node-6.x-xxxx.sles.10sp2.x86\_64.rpm | SUSE Linux Enterprise Server 10 SP2 64位 |
| info2soft-i2node-6.x-xxxx.sles.11sp1.x86\_64.rpm | SUSE Linux Enterprise Server 11 SP1 64位 |
| info2soft-i2node-6.x-xxxx.sles.11sp2.x86\_64.rpm | SUSE Linux Enterprise Server 11 SP2 64位 |
| info2soft-i2node-6.x-xxxx.sles.11sp3.x86\_64.rpm | SUSE Linux Enterprise Server 11 SP3 64位 |
| info2soft-i2node-6.x-xxxxx.sles.11sp4.x86\_64.rpm | SUSE Linux Enterprise Server 11SP4 64位 |
| info2soft-i2node-6.x-xxxx.ubuntu.12.04.2.x86\_64.deb | Ubuntu 12.04.2 64位 |
| info2soft-i2node-6.x-xxxxx.ubuntu.12.04.3.x86\_64.deb | Ubuntu 12.04.3 64位 |
| info2soft-i2node-6.x-xxxxx.ubuntu.12.04.4.x86\_64.deb | Ubuntu 12.04.4 64位 |
| info2soft-i2node-6.x-xxxxx.ubuntu.14.04.3.x86\_64.deb | Ubuntu 14.04.3 64位 |
| info2soft-i2node-6.x-xxxxx.ubuntu.14.04.x86\_64.deb | Ubuntu 14.04.3 64位 |
| info2soft-i2node-6.x-xxxxx.ubuntu.16.04.2.x86\_64.deb | Ubuntu 16.04.2 64位 |
| info2soft-i2node-6.x-xxxxx.uek7.x86\_64.rpm | oracle linux 7系列64位 |
| info2soft-i2node-6.x-xxxx.debian.7.1.x86\_64.deb | Debian 7.1 64位 |
| info2soft-i2node-6.x-xxxx.debian.7.4.x86\_64.deb | Debian 7.4 64位 |

I2控制机安装平台支持的是：el6系列、el7系列，以及Windows XP SP3、Windows Server 2008和Windows 7及win7以上系统，支持32位和64位平台，如以版本6.1-xxxx为例，对应安装包参考如下列表：

| ctrlcenter安装包名称 | 操作系统版本 |
| --- | --- |
| info2soft-ctrlcenter-6.x-xxxx.exe | Windows XP SP3、Windows 7及win7以上系统 |
| info2soft-ctrlcenter-6.x-xxxx.el6.i686.rpm | RHEL6、CentOS6以上系列 32位 |
| info2soft-ctrlcenter-6.x-xxxx.el6.x86\_64.rpm | RHEL6、CentOS6以上系列 64位 |
| info2soft-ctrlcenter-6.x-xxxxx.el7.x86\_64.rpm | CentOS7系列64位 |
| info2soft-ctrlcenter-6.x-xxxxx.sles.11sp3.x86\_64.rpm | suse 11 sp3 |
| info2soft-ctrlcenter-6.x-xxxxx.sles.11sp4.x86\_64.rpm | suse 11 sp4 |

注意：所有模块的安装必须在Linux/Unix root用户、Windows administrator用户或具有相关超级权限的用户下进行。

* [节点\(i2Node\)安装](node_install.md)
* [控制机\(i2CtrlCenter\)安装](ctrl_install.md)
* [软件卸载](soft_uninstall.md)



