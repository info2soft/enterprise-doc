# 全服务器保护

i2软件提供服务器迁移、备份和还原。迁移是在不停机的情况下将整个系统迁移到指定机器。备份是在不停机情况下将整个系统备份到备机暂存，还原是根据客户需要将备份在备机的系统还原到指定机器上。

要实现服务器备份，确保工作机和灾备机对应关系：Linux-&gt;Linux、Windows-&gt;Windows或Windows-&gt;Linux；备机服务器要有足够的磁盘空间；

全服务器还原是在全服务器备份的基础之上的，可以将备份到灾备机上的数据、应用等还原到客户端；

全服务器迁移，即，可以将主机的网络、数据、系统状态全部备份到备机，如果需要，用户可以手动从主机切换到备机，从而实现服务器的迁移。

 * [全服务器迁移](move.md)
 * [全服务器备份](backup.md)
 * [全服务器还原](restore.md)

