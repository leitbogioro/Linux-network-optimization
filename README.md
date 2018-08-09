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
<br />
<br />
<br />
<br />
