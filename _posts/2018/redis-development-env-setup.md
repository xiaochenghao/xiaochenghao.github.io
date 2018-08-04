环境：CentOS7、Redis

主要解决Jedis客户端无法连接Linux上Redis服务问题


1、修改Redis目录下的redis.conf配置文件

      注释掉bind本地回环地址：bind 127.0.0.1
      如果未设置Redis认证密码，则需要设置保护模式为no：protected-mode no

2、停止CentOS7防火墙或设置规则（这里使用停止方法）

　　systemctl stop firewalld.service
　　systemctl stop iptables.service
