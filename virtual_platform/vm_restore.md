## 虚机恢复

### 添加恢复规则 {#-0}

在控制机管理界面，通过 虚拟化支持-&gt;虚机恢复，来添加/编辑恢复规则，恢复规则添加/编辑页面如下：

![](/assets/V7.1.2019011513.png)

*   “规则名称”：客户命名的名称，便于管理；
*   “灾备机”：储存备份数据的备机；
*   “数据存放目录”：选择备份数据储存的路径；
*   “恢复类型”： 可以选择“普通恢复”和“瞬时恢复”两种方式；
*   “选择备份点”：备份数据的备份时间及大小，注意这里必须选择一个备点，才能显示备份点信息，才能建立恢复规则；

当选择组恢复时，页面如下：

![](/assets/V7.1.2019011514.png)

* “组别名称”：备份规则组别的名称；

### 高级设置 {#-1}


![](/assets/V7.120190325122726.png)

*    “创建新虚机”：不勾选表示恢复到原来的虚机，勾选表示恢复到新创建的虚机；
*    “恢复完成自动开机”: 不勾选表示恢复完成后恢复的虚机处于关机状态，勾选表示恢复完成后恢复的的虚机处于开机状态；
*    “支持LAN Free”: 在LAN-FREE模式可用时，使用san方式传输；
*    “虚拟机”：恢复的虚机所用的名称，不能和现有的虚机重名，不能包含特殊字符；
*    “目标平台”：恢复的目标虚拟平台；
*    “数据中心”：目标虚拟平台的数据中心；
*    “主机名称”：目标虚拟平台的主机名称；
*    “数据存储”：目标虚拟平台的数据存储磁盘；
*    “处理器数量”：根据需求设定目标虚机的处理器数量；
*    “处理器核心数量”：根据需求设定目标虚机的处理器核心数量；
*    “内存”：根据需求设定目标虚机的内存大小；
*    “MAC地址”：如果不修改这个默认值，则恢复的虚机的MAC地址会和源虚机一样，如果不希望和源虚机用一样的MAC地址，则需要在页面上删除MAC地址，虚机在创建时会分配新的MAC地址，删除MAC地址后，页面显示如下：
*   “工作目录”：只有勾选了“创建新虚机”才会出现此选项，只有目标虚拟平台是esxi平台有此选项，表示新创建的虚机所在的目录；
*    “磁盘列表”：在基本设置中选择完备份时间点后，虚拟机磁盘列表显示相对应的虚拟机磁盘，只有勾选了“创建新虚机”，才会出现“数据存储”，“磁盘路径”，“是否与工作目录一致”，此时可选择创建新虚机的磁盘存储和磁盘路径；

### 带宽控制 {#-0}

![说明: 1](/assets/V7.020190108192204.png)

### 恢复规则列表 {#-2}

添加恢复任务后，页面如下：

![](/assets/V7.120190404151719.png)

恢复规则包含如下状态：

*    “启动”：恢复规则开始启动；
*    “排队中”：任务正在排队；
*    “创建新虚机”： 开始创建虚拟机；
*    “获取虚机配置”：获取虚拟机配置信息到备机；
*    “查询变化数据”：计算变化块并保存到备机；
*    “传输中”：显示恢复进度百分比；
*    “停止”：规则停止；
*    “失效”：npsvr或备机宕机出现失效状态；
*    “完成”：恢复规则完成；
*    “恢复快照”：将目标虚机转到之前创建的快照；
*    “快照清除”：目标虚机转到之前创建的快照之后，将快照移除；

针对恢复规则可用的操作，从左到右如下：

*   “启动”：启动此虚机的规则；
*   “停止”：停止此虚机的规则；
*   “删除”：删除此虚机的规则；
*   “查看日志”：查看此虚机的日志；
*   “查看统计信息”：查看此虚机的统计信息；

组操作栏可用操作如下：

*   “查看配置”：查看恢复规则的配置；
*   “查看统计信息”：查看恢复规则的统计信息；
*   “组启动/组停止/组删除”：启动，停止，删除组规则；




## 瞬时恢复

瞬时恢复与虚机恢复相比，不会将备份数据写入到新虚机磁盘，当创建了一台空磁盘虚机并启动后，新的虚机会去读取备份数据，进行启动和显示，当写入新数据后，将写入的数据写入到新虚机中；

新建一个瞬时恢复，流程如下：

1.NpServer让灾备机启动fuse和nfs；

2.NpServer将nfs挂载到ESXI并创建虚拟机；

3.NpServer下发信息，让灾备机将备份数据发给fuse，之后fuse独立运行，直接将数据写入到新虚拟机磁盘中；

瞬时恢复目前只支持灾备机为RHEL或CENTOS 6.5 64位以上操作系统，但不支持RHEL或CENTOS7;

由于受到NFS挂载的限制，瞬时恢复的虚机只支持精简置备，不管源虚机是什么磁盘类型；

瞬时恢复没有带宽控制选项；

### 瞬时恢复基本设置 {#-0}

![说明: 1](/assets/V7.020190109174423.png)

### 瞬时恢复高级设置 {#-0}

![说明: 1](/assets/V7.020190109174438.png)


瞬时恢复规则包含如下状态：

*    “运行”：规则正在运行；
*    “停止”：规则停止；

针对瞬时恢复规则可用的操作包括：

*   “启动”：启动此虚机的规则；
*   “停止”：停止此虚机的规则；
*   “删除”：删除此虚机的规则；


### 瞬时恢复环境搭建步骤 {#-4}

**灾备机是Centos6.5_64bit操作系统**

* yum install fuse fuse\* fuse-\*
* yum install gcc gcc-c++
* yum install nfs nfs\*
* yum install rpcbind
* /etc/init.d/rpcbind start
* /etc/init.d/nfs start
* 新建目录/root/disk/nfs，作为nfs共享的目录
* chown -R nfsnobody:nfsnobody /root/disk/nfs
* 修改/etc/exports文件如下：

[root@localhost /]# cat /etc/exports

/root/disk/nfs 192.168.0.0/16(rw,no_root_squash,nohide,sync,fsid=0,anonuid=501,anongid=501)

其中“/root/disk/nfs”是nfs共享的目录, “192.168.0.0/16” 有权共享本目录的IP网段，“rw”表示来访者对所共享出去的目录享有读和写的权力，"no_root_squash"表示如果来访者是该机的 root 则在本机也给予 root 待遇，“nohide”表示共享NFS目录的子目录，“sync”表示资料同步写入到内存与硬盘中。

* /etc/init.d/nfs restart
* 新建目录/root/disk/tmp，用来存放新建的虚拟机
* chown -R nfsnobody:nfsnobody /root/disk/tmp
* 检查/usr/local/sdata/sbin目录下是否有fuse_start文件
* 检查/usr/local/sdata/scripts目录下是否有fuse_script.sh文件
* 修改/etc/sdata/system.conf文件(如果文件不存在，则新建system.conf文件)

文件中存放三个变量：fuse_script, tmpdir, nfsdir三者缺一不可。

[root@localhost sdata]# cat system.conf

fuse_script=/usr/local/sdata/scripts/fuse_script.sh

tmpdir=/root/disk/tmp

nfsdir=/root/disk/nfs

其中“fuse_script”表示的是脚本执行路径，“tmpdir”是实际存储的虚拟机的位置，“nfsdir”实际上是fuse将tmpdir映射到nfsdir，并且nfsdir目录是nfs目录，nfsdir路径中的目录需要与/etc/exports中的目录对应上。

* service i2node restart

* 防火墙不能屏蔽对fuse和nfs的执行，否则esxi上无法挂载nfs存储。

由于nfs服务需要开启 mountd, nfs, nlockmgr, portmapper, rquotad这5个服务，需要将这5个服务的端口加到iptables里面。而nfs和portmapper两个服务是固定端口的，nfs为2049，portmapper为111，其他的3个服务是用的随机端口，那就需要先把这3个服务的端口设置成固定的，用命令rpcinfo -p 查看当前这5个服务的端口，并记录下来。  

nfs 2049, portmapper 111, mountd 42367, rquotad 875,nlockmgr 48844

设置/etc/sysconfig/nfs配置文件，配置端口使rquotad，nlockmgr，mountd的端口固定，添加如下几行：

RQUOTAD_PORT=875

LOCKD_TCPPORT=48844

LOCKD_UDPPORT=48844

MOUNTD_PORT=42367

重启nfs服务，/etc/init.d/nfs restart

在防火墙中开放这5个端口, 在/etc/sysconfig/iptables添加如下几行，必须加在icmp-host-prohibited那两行之前：

-A INPUT -p tcp -s 192.168.0.0/16 --dport 111 -j ACCEPT

-A INPUT -p udp -s 192.168.0.0/16 --dport 111 -j ACCEPT

-A INPUT -p tcp -s 192.168.0.0/16 --dport 2049 -j ACCEPT

-A INPUT -p udp -s 192.168.0.0/16 --dport 2049 -j ACCEPT

-A INPUT -p tcp -s 192.168.0.0/16 --dport 42367 -j ACCEPT

-A INPUT -p udp -s 192.168.0.0/16 --dport 42367 -j ACCEPT

-A INPUT -p tcp -s 192.168.0.0/16 --dport 875 -j ACCEPT

-A INPUT -p udp -s 192.168.0.0/16 --dport 875 -j ACCEPT

-A INPUT -p tcp -s 192.168.0.0/16 --dport 48844 -j ACCEPT

-A INPUT -p udp -s 192.168.0.0/16 --dport 48844 -j ACCEPT

![说明: 1](/assets/20190404125335.png)

重启防火墙：service iptables restart

* 重启i2node服务，service i2node restart

* 如果此台机器安装了npsvr软件，重启npsvr服务，service npsvr restart

* 查看防火墙规则，执行iptables --list

![说明: 1](/assets/20190404125356.png)

* 页面上添加节点和虚拟平台

* 新建虚机备份任务

![说明: 1](/assets/V7.120190404153244.png)

* 新建瞬时恢复任务

![说明: 1](/assets/V7.120190404153310.png)

* 灾备机：

![说明: 1](/assets/20190404125302.png)

* esxi平台：

![说明: 1](/assets/esxi-platform.png)
