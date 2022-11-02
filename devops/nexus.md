#### nexus私服搭建
##### 官网下载nexus的安装包latest-unit.tar.gz
由于官网下载过慢，此处提供百度网盘的下载地址[百度网盘](https://pan.baidu.com/s/1JswZhQaMURb8CClA_Dw2GQ)，提取码：enj3

+ 解压tar包
  解压后有nexus-3.14.1-01文件夹和sonatype-work文件夹
+ nexus-3.14.1-01目录中配置端口等属性
  etc/nexus-default.properties
+ 启动bin/nexus (推荐使用非root用户)
  + start/stop/status/restart
+ 浏览器打开控制台
  + 如果应用已启动，但是无法打开。请配置防火墙
    ```
    # centOS系统环境
    vi /etc/sysconfig/iptables  
    # 增加如下配置：
    -A INPUT -p tcp -m state --state NEW -m tcp --dport 8081 -j ACCEPT
    ```

  + 重启防火墙：service iptables restart
 + 可以正常打开后，sign in时，请参考提示文件找到admin的密码
 + 创建新用户，避免直接提供admin给使用人员
 + 执行npm login --registry=url   
   + E401——请用admin账户登录后setting/security/Realms/active [npm Bearer Token Realm]，
   + E409——执行npm config list，找到.npmrc中，删除或者修改已存在的token信息后重新登录
  
##### 数据迁移
  旧环境的sonatype-work替换新环境中解压出来的目录即可
###### sonatype-work资源
[适用于v2.7的版本](待提供地址)

