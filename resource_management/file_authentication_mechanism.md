## 文件认证机制

I2提供文件认证机制，客户在节点认证时如果不方便输入系统用户名和密码，就可以通过文件认证机制来自定义登录的用户名以及密码；

### Windows认证 {#windows}

在&lt;安装路径&gt;\etc\目录下增加auth.conf文件，文件内容如下：

auth_user=xxxx

auth_passwd=yyyy

### Linux认证 {#linux}

在/etc/sdata/目录下增加auth.conf文件，文件内容如下：

auth_user=xxxx

auth_passwd=yyyy

登录时，检查用户输入的用户名、密码是否和auth.conf中的“xxxx”和“yyyy”匹配，如果匹配，则认证成功；