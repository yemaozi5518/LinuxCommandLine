# LinuxCommandLine
###### 要使用命令行，可以先确定自己喜欢的shell(脚本工具)
#### 查看当前的shell
 - echo $SHELL
#### 查看所有可用shell
 - 1 
    - chsh -l
 - 2
    - cat /etc/shells
###### https://blog.csdn.net/u013943420/article/details/82051467
#### 修改为指定的shell
 - 1 
   - chsh -s [shell路径]
 - 2
   - chsh 用户名
   - 输入shell路径
 - 3 找到用户信息并修改（具体可以补充linux文件结构和管理）
   - vim /etc/passwd
## 在安装软件时，可能需要的下载工具，需要先行安装
 - wget
 - git
 - npm (node)
 - 安装 nginx 需要安装firewall和ipservices
   - nginx php 跨站攻击解决策略
      - conf/nginx.conf.d 下 test.conf
      - 正则校验php请求
      - 开启 SecRulesEnabled ,并配置白名单（
        baserule 例子: BasicRule wl:1315 "mz:$HEADERS_VAR:Cookie";
        配置语法：搜索)
      - 查看Nginx作为webService服务器的拦截规则 vim naxsi_core.rules
         例子 ： BasicRule wl:1315 "mz:$HEADERS_VAR:Cookie";
 - 解压缩工具  tar  xz 等
#### Linux查看版本当前操作系统内核信息
 - uname -a
#### Linux查看当前操作系统版本信息
 - cat /proc/version
#### Linux查看版本当前操作系统发行版信息
 ###### 此命令也适用于所有的Linux发行版
 - cat /etc/issue  
 ###### 这种方法只适合Redhat系的Linux
 - cat /etc/redhat-release
#### Linux查看cpu相关信息，包括型号、主频、内核信息等
 - cat /proc/cpuinfo
#### Linux查看版本说明当前CPU运行在32bit模式下， 但不代表CPU不支持64bit
 - getconf LONG_BIT
#### 查询所有版本信息：
 - lsb_release -a
