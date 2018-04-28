### centos 安装nginx步骤

```
$ vi /etc/yum.repos.d/nginx.repo
```
把文本粘贴进去
```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/OS/OSRELEASE/$basearch/
gpgcheck=0
enabled=1
```
> baseurl 中的OS 换成centos , OSRELEASE 换成6或7     (cat /etc/redhat-release 可以查看当前centos的版本)

 1. 新建一个nginx_signing.key 文件(vi nginx_signing.key)
 2.打开[nginx_signing.key](https://nginx.org/keys/nginx_signing.key),把内容粘贴到 nginx_signing.key 文件里面,保存退出。
 ```
 $ sudo rpm --import nginx_signing.key
 $ yum -y install nginx
 $ nginx
 $ curl 127.0.0.1 （会出现html,标识成功）
 ```

> 去/etc/nginx/conf.d文件下选择去添加或者修改配置文件
