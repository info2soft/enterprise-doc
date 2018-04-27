## i2控制机安装 {#i2}

### Windows安装 {#windows}

Windows下安装控制机过程与安装i2node类似，这里不再介绍，请参考i2node安装过程。Windows控制机安装包含

Apache、PHP、Postgresql和i2控制机界面，安装之前用户请确保安装环境中**不存在已有的Postgresql服务**。

安装完成后，进入计算机管理-&gt;服务，确认Apache24-i2以及Postgresql-i2服务已启动。

![](/assets/V6.113850.png)

![](/assets/V6.113852.png)

然后通过任意的一台主机只要能访问到控制机，即可通过浏览器登录到Web控制页面进行操作，注意英方控制机6.1兼容的

浏览器是IE8+、Firefox12+、Chrome15+，如控制机的IP地址为192.168.100.102，则访问地址为：

[http://192.168.100.102:58080/](http://192.168.100.102:58080/)或者是[https://192.168.100.102:55443/](https://192.168.100.102:55443/)

也可以在本机使用i2CtrlApp应用程序登陆操作

### Linux安装 {#linux}

打开终端或者Xshell/putty连接到服务器，以命令行安装方式为例：

![](/assets/V6.114130.png)

根据依赖关系的先后安装相关的rpm包后，如果能联网，依赖包可通过

`yum install info2soft-ctrlcenter-6.x-xxxxx.el6.x86_64.rpm`

来安装依赖包，再次执行控制机模块的安装命令：

\[root@localhost ~\]\#rpm -ivh info2soft-ctrlcenter-6.x-xxxxx.el6.x86\_64.rpm

注意：RHEL6.X/CentOS6.X/CentOS7.x系统第一次安装控制机需要初始化数据库PostgreSQL

![](/assets/V6.114289.png)

Centos7 ：postgresql-setup initdb \#初始化数据库

![](/assets/V6.114290.png)

安装完之后，下列后台守护进程已经运行：

![](/assets/V6.114313.png)

如果控制机重启，或其他异常导致控制机守护进程未正常启动，可通过下列命令手工启动：

![](/assets/V6.114356.png)

然后通过任意的一台主机只要能访问到控制机，即可通过浏览器登录到Web控制页面进行操作，注意i2控制机完美兼容的浏览器是IE8以上、Firefox12以上、Chrome15以上，如控制机的IP地址为192.168.100.102，则访问地址为：

[http://192.168.100.102:58080/或者是https://192.168.100.102:55443/](http://192.168.100.102:58080/或者是https://192.168.100.102:55443/)

