file: command.md

# 网络相关命令
`netstat -ni` 
- `-i` interface 
- `-n` numeric 
- `-r` route 路由表
- `a` 查看所有
- 可以查看TCP状态转换

`lsof`
    - 含义：list open files，列出打开的文件
    - 可以对netstat进行补充，因为其可以列出进程名
    - `lsof -i TCP:daytime`

`ifconfig [interface]`
- `interface` 接口名可以通过`netstat -i`查询
- `-a` 输出所有已配置接口信息
- `ifconfig eth0 down/up` 关闭/启动指定显卡
- https://www.runoob.com/linux/linux-comm-ifconfig.html

`ping`
- `ping -b ip地址` 找出本地网络中众多主机IP地址。参数`ip地址`是ifconfig输出的broadcast地址
- 该应用利用ICMP协议回送请求和应答报文，其测试用的IP数据报为84字节

`traceroute`
    - 该应用利用ICMP协议进行网络诊断
    - 自行构造UDP分组来发送并读取所引发的ICMP应答


`ssh`或`rsh`
`route` 显示/控制路由表
`tracert`
`telnet`


`hostname` 查看主机名称
    - `-i` 查看主机对应的IP

`inetd` 守护进程，提供`echo`, `discard`, `daytime`, `chargen`, `time`等标准服务，这些服务由`/etc/services`映射到相应的端口上。

`nc` netcat，可以用来作为客户端，以测试服务器程序

`tcpdump` 抓包
    `tcpdump -i lo port 9877` 监视127.0.0.1:9877，其中lo是网络接口名，由ifconfig可以查看
    `tcpdump port 80 or port 8080` 监视80或8080端口，这里应该会使用默认网口


## 系统相关命令
`sysctl` 被用于在内核运行时动态地修改内核的运行参数，可用的内核参数在目录/proc/sys中。它包含一些TCP/ip堆栈和虚拟内存系统的高级选项，这可以让有经验的管理员提高引人注目的系统性能。用sysctl可以读取设置超过五百个系统变量。