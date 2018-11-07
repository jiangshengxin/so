# so
This is a SSH login tool


## Linux ssh 登陆工具:

###　一.说明
- 支持密码和密钥两种格式,推荐使用密钥
- 用户名和密码都是写文件的,明文保存

### 二.配置
- 密码文件配置:

序号:IP:端口:用户:密码:说明  
1:192.168.88.128:22:root:password:虚拟机web服务器  
2:192.168.88.129:22:root:name.pem:虚拟机web服务器2

- 密钥文件放在keys文件夹下,密码位置写成密钥文件名,文件名必须以.pem结尾


- 密钥目录及密钥文件权限(必须) : 

chmod -R 600 ./keys/  
chmod 644 ./LICENSE  
chmod 755 ./so*

[root@jiangshengxin so]# ll  
total 44  
drw------- 2 root root  4096 Nov  7 17:17 keys  
-rw-r--r-- 1 root root 18047 Nov  7 14:21 LICENSE  
-rw------- 1 root root   177 Nov  7 17:17 password.lst  
-rw-r--r-- 1 root root  1083 Nov  7 17:17 README.md  
-rwxr-xr-x 1 root root  1925 Nov  7 17:29 so  
-rwxr-xr-x 1 root root  1925 Nov  7 17:17 so.sh  
-rw-r--r-- 1 root root   277 Nov  7 14:21 ssh_login.exp  


- 远程登录
[root@jiangshengxin so]# ./so.sh  
==============================================  
    SSH Login 提示,从远程主机退出命令:exit      
==============================================  

序号 |       主机      | 说明
-----------------------------------------  
  1  |    192.168.88.128 | 虚拟机web服务器  
  2  |    192.168.88.129 | 虚拟机web服务器2  
-----------------------------------------  
[*] 选择主机: q


- 加入系统命令  
[root@jiangshengxin so]# vim /etc/profile  
PATH=$PATH:/var/so  
export PATH  
[root@jiangshengxin so]# source /etc/profile
