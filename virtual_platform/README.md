# 无代理备份（i2vp） {#i2vp}

i2软件提供无代理虚机备份（i2VP），无代理虚机备份为虚拟化环境中虚拟机整机保护而设计，且备份的数据是基于快照的。支持虚拟机备份，虚拟机恢复原机和异机重建恢复。

无代理虚机备份也有工作机和灾备机，不同于i2企业版三层结构的地方在于工作机变成了虚拟化平台，对于虚拟平台，在控制机和工作机之间还加入了一个通信服务：NPSVR。NPSVR负责规则管理、虚拟化平台管理、日志收集、与灾备机通信。在备份虚拟平台上的虚机时，控制机不再直接与虚拟平台和灾备机通信，而是通NPSVR来间接通信。


下图是针对VMWware虚拟平台的基本架构

![](/assets/V6.139984.png)


下图是针对Hyper-V虚拟平台的基本架构

![](/assets/hyperv-structure2.png)


对于Hyper-V虚拟平台，在添加虚拟平台的时候，会在Hyper-V主机上远程静默安装Data Agent软件，删除虚拟平台的时候，会远程静默卸载Data Agent软件。
Data Agent安装过程中生成系统环境变量I2DATAAGENT，变量的值为安装目录。
Data Agent软件是负责Hyper-V主机和备机之间，虚拟机数据的传输。

添加Hyper-V虚拟平台之前，Hyper-V主机需要做如下准备工作：

以管理员权限运行cmd，执行如下2条命令:
winrm quickconfig
winrm set winrm/config/service @{AllowUnencrypted="true“}

防火墙，允许应用-windows远程管理(兼容)，出入站端口：5985/5986


* [NpServer部署](install_npsvr.md)
* [虚机备份](vm_backup.md)
* [虚机迁移](vm_move.md)
* [虚机恢复](vm_restore.md)
* [虚机复制](vm_rep.md)



