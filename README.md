安装mininet遇到的问题
1，virtual box 安装虚拟机 eth1的dhcp分配的地址是10开头和本机的私有地址不一样，本机是198？

2，eth0为啥没地址了,原因如下
ubuntu开机出现下面打印：

waiting for network configuration then:  

waiting an additional 60 seconds for network configuration  

修复

在/etc/init/failsafe.conf中注释掉相关打印即可。

3, ssh提示Host key verification failed 
  原因是在主机子系统每次成功ssh连接远程操作，都会把你每个你访问过计算机的公钥(public key)都记录在主机的目录/root/.ssh的known_hosts下，当下次访问相同子机服务器时，会核对公钥。如果公钥不同，会发出警告，避免你受到DNS Hijack之类的攻击。
