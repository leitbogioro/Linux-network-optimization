# Linux 网络优化脚本
# Linux-network-optimization
<br />
<br />
这是一个Linux的优化小脚本
<br />
<br />
优化内容：
<br />
<br />
1. 写入 /etc/profile 的内容
<br />
<br />
<code>ulimit -SHn 1024000</code>
<br />
<br />
作用：增大Linux系统open file(s)的上限
<br />
<br />
2. 写入 /etc/security/limits.conf 的内容
<br />
<br />
作用：使文件句柄数更改完全生效
<br />
<br />
<code>* soft nofile 1024000</code>
<br />
<br />
<code>* hard nofile 1024000</code>
<br />
<br />
3. 开启 hybla 算法
<br />
<br />
解释：适用于高延时、高丢包率的网络，比如卫星链路——适用于中美之间的链路。
<br />
<br />
<code>/sbin/modprobe tcp_hybla</code>
<br />
<br />
3. 如果已安装魔改版bbr，向
<br />
<br />
<br />
<br />
