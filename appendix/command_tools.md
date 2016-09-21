## 工作机（生产机）数据变化量诊断工具

在广域网环境中，带宽是很重要和昂贵的资源，用户希望充分而有效的利用带宽资源。一方面，不能因为带宽资源不足而使业务受到影响，另一方面，也不希望带宽资源得不到充分利用而浪费。用户在利用英方软件进行数据异地容灾保护时，常常遇到一个疑问：该购买或者分配多大的带宽资源给英方软件？英方软件推出工作机（生产机）数据变化量诊断工具，用来诊断工作机（生产机）的数据变化量，以及所需要的带宽。

工作机（生产机）数据变化量诊断工具使用方法如下：

1.  安装英方软件工作机/灾备机软件到用户生产机上。
2.  调用命令添加诊断任务：

Windows系统：

打开Windows命令行（cmd）：

cd &lt;info2soft installation path&gt;\bin

repset -A &quot;diagtraffic&quot; -f &quot;C:\\data2\\&quot; -f &quot;C:\\data3\\test.mdf&quot; -f &quot;C:\\java\\&quot; –i

说明：

1.  info2soft installation path 默认x64系统在C:\Program Files (x86)下， 32位系统在Program Files目录下，例如：C:\Program Files (x86)\info2soft-i2node
2.  命令说明：-A &quot;diagtraffic&quot;: 指定诊断任务的名字，引号中的字符可以任意；

-f 指定监控数据的目录，多个文件或者目录，需要多个-f参数。注意引号中的文件分割符\\, 代表Windows的文件分割符\, 目录必须以\\结尾；

Linux系统：

#repset -A &quot;diagtraffic&quot; -f &quot;/home/data2/&quot; -f &quot;/home/data3/test.mdf&quot; -f &quot;/home/java/&quot; –i

1.  查看变化的数据量：

Windows系统：

cd &lt;info2soft installation path&gt;\bin

repset -L

Linux系统

Repset -L

如下个例子：

diagtraffic REPLICATION

sourcepath: C:\data2\ C:\data3\ C:\java\

uuid: 0A14EA7F-AC7F-E646-AF4A-F4151574A978

diagnosis mode: time=0h 32m 56s total=1.12GB

speed=594.02KB/s maxspeed=65.58MB/s

说明：规则总共运行了32分56秒，总的数据变化量为：1.12GB，平均数据变化率为：594.02KB/s，最大的数据变化率为：65.58MB/s

1.  在完成诊断任务之后，需要删除诊断任务

Windows系统：

cd &lt;info2soft installation path&gt;\bin

repset -D &quot;diagtraffic&quot;

Linux系统

#repset -D &quot;diagtraffic&quot;

通常，我们推荐选择具有典型业务或者业务量较大的一天，运行数据变化量诊断工具，得到数据变化总量和平均变化量。平均变化量代表传输这些变化的数据所需要的最小带宽。当然，系统在传输这些数据的时候有一些额外的开销，以及考虑到实际的数据变化可能存在一些波动，实际需要的带宽应该比这个更高。如果下是我们推荐的带宽计算公式：

&lt;平均数据变化率&gt; x 1.25 (考虑而外开销数数据变化波动) x 1.25 (通常实际带宽只能达到你所购买带宽的80%) x 8 （B-&gt;b的转化）

如上面的例子，用户需要的带宽为：

594.02KB/s x 1.25 x 1.25 x 8 = 7.4Mbps