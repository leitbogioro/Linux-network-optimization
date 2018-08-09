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
4. 如果已安装魔改版bbr，向/etc/sysctl.conf 写入以下内容
<br />
<br />
max open files
<br />
<br />
fs.file-max = 1024000
<br />
<br />
max read buffer
<br />
<br />
net.core.rmem_max = 67108864
<br />
<br />
max write buffer
<br />
<br />
net.core.wmem_max = 67108864
<br />
<br />
default read buffer
<br />
<br />
net.core.rmem_default = 65536
<br />
<br />
default write buffer
<br />
<br />
net.core.wmem_default = 65536
<br />
<br />
max processor input queue
<br />
<br />
net.core.netdev_max_backlog = 4096
<br />
<br />
max backlog
<br />
<br />
net.core.somaxconn = 4096
<br />
<br />
<br />
<br />
resist SYN flood attacks
<br />
<br />
net.ipv4.tcp_syncookies = 1
<br />
<br />
reuse timewait sockets when safe
<br />
<br />
net.ipv4.tcp_tw_reuse = 1
<br />
<br />
turn off fast timewait sockets recycling
<br />
<br />
net.ipv4.tcp_tw_recycle = 0
<br />
<br />
short FIN timeout
<br />
<br />
net.ipv4.tcp_fin_timeout = 30
<br />
<br />
short keepalive time
<br />
<br />
net.ipv4.tcp_keepalive_time = 1200
<br />
<br />
outbound port range
<br />
<br />
net.ipv4.ip_local_port_range = 10000 65000
<br />
<br />
max SYN backlog
<br />
<br />
net.ipv4.tcp_max_syn_backlog = 4096
<br />
<br />
max timewait sockets held by system simultaneously
<br />
<br />
net.ipv4.tcp_max_tw_buckets = 5000
<br />
<br />
TCP receive buffer
<br />
<br />
net.ipv4.tcp_rmem = 4096 87380 67108864
<br />
<br />
TCP write buffer
<br />
<br />
net.ipv4.tcp_wmem = 4096 65536 67108864
<br />
<br />
turn on path MTU discovery
<br />
<br />
net.ipv4.tcp_mtu_probing = 1
<br />
<br />
<br />
<br />
for high-latency network
<br />
<br />
net.ipv4.tcp_congestion_control = hybla
<br />
<br />
forward ipv4
<br />
<br />
net.ipv4.ip_forward = 1
<br />
<br />
