# 1.命令入门 
## 1. ls 命令 
### 1.作用 
可以制定要查看的文件夹的内容 
### 2.选项 
-a 展示隐藏的内容 
- l 以列表形式展开 
- h 需要和-l搭配使用 ， 展示大小单位
### 3. 可以组合使用 
ls -lah , 等同于 ls -a -l -h 
##  2. cd 命令
### 使用 
cd命令无需选项 ，只有参数 ，表示要切换到那个目录下面 
cd命令直接执行 ，不写参数 ， 表示回到用户的HOME目录 
根目录 cd / 
例如bin 目录下 cd /bin  
////////////////////////////////////////////////////////////////////  
使用时 切换目录下 直接目录未成功， 需要携带之前的目录 
例如var下面的 games 目录 
在 var下 ，/games不成功 ， /var/games成功 
## 3.pwd
### 使用 
查看当前工作目录 
## 4.相对路径和绝对路径 
### 1.路径问题 
绝对路径 /cd /home/user/Desktop
相对路径 cd Desktop
### 2.特殊路径付 
. 当前目录    cd 
.. 上一级目录 cd ..
~ 表示HOME目录 cd~ 
## 5.mkdir指令 
### 1.定义 
通过mkdir命令可以创建新的目录 
相对路径 mkdir     itheima1 
绝对路径 mkdir     /home/user/test 
mkdir -p 创造所创造文件的父目录  
mkdir itcast/good/666  HOME范围内 ， 权限范围
## 6.文件操作命令 touch/cat/more
###  1. touch指令 
创建文件 
touch 360.txt
### 2. cat命令 
查看文件内容 cat 相对/绝对/特殊路径
一次全部展示文件内容 
### 3.more命令 
同样可以查看文件内容 
more支持翻页 ， 如果内容过多 ， 可以一页页展示 
查看过程 空格 翻页  q 终止 
## 7.cp-mv-rm命令 
### 7.1 cp 
复制命令(copy) 
cp [-r] 被复制的文件 要复制去的地址 
### 7.2 mv命令 
用于移动文件\文件夹 
mv 参数1 参数2     

mv test.txt Desktop/

改名效果 mv   text2.txt    test3.txt

## 7.3 rm命令

删除 

rm text.txt  文件 

rm -r text  文件夹

通配符 test* 
*test  *  模糊匹配

## 7.4 root用户

su - root  密码 

exit 退出管理员模式 

## 7.5 which 命令 

查看所使用的一系列命令的程序文件存放在那里

which cd 

## 7.6 find 命令 

 find  / -name "test"

  按照文件大小查找 find / -size -10M

## 7.7 wc命令 

wc [ -c -m -l -w ] 路径

 bytes数量 ， 字符数量 ， 行数 ， 单词数量 

## 7.8 grep命令 

grep "itheima" 360.txt 搜索标红

grep -n "code" text.txt  显示行号 ，标记位置

## 7.9 管道符 

前面输出的结果 作为后面输入的内容

cat 360.txt | grep itheima  

cat  360.txt | wc -l

 嵌套使用  

cat 360.txt | grep itheima | grep itcast

##  8.0 echo 命令 

1.   echo "输出内容 "
2.   echo ````pwd`````  
   漂号中间的内容被当做程序执行 只有一对 
## 8.1 重定向符 
1.  将左侧命令的结果 ， 覆盖到右侧的文件中  >
2. 左侧命令的结果    ，  追加到右侧的文件中  >> 
## 8.2 tail命令
1. 查看文件尾部内容 跟踪文件 
2. tail [-f -num] 路径 
3. -f 持续追踪  
4. -num 查看尾部多少行 ， 默认 10 
## 8.3 Ctrl + C  
1. 强行终止指令 
## 8.4 vi 编辑器 
命令模式 :  所敲的按键理解为命令 ， 驱动执行不同功能 
输入模式： 编辑模式
底线命令模式： 通常文件的保存 ， 退出 
 1. vim hello.txt （创建） 
 2. i (进入输入模式) 
 3. liuzhendong is a hero 
 4. Esc 退出 ， 回到命令模式 
 5. : 进入底线模式 
 6. wq 保存并退出 
## 8.5 vim 快捷指令 
------------------   命令模式 -----------------

1. dd 删除所在行 
2. yy 复制当前行 
3. p 粘贴复制的内容
4. u 撤销修改 
    --------     底线命令模式 --------------
5. :q! 强制退出 
6. ：set nu 显示行号 
7. ： set paste 设置粘贴模式  
# 2. 权限信息
## 1.1 root管理 
sudo 命令  可以让一些普通命令拥有root权限 
root 用户执行visudo 命令 ，添加 
## 1.2 用户组 
使用root用户执行 
1. group 添加组 ， groupdel删除组

2. useradd 添加用户 ， userdel 删除用户

3. usermod修改用户组 ， id命令查看用户信息 

4. getent passwd 查看系统全部用户信息 ： 用户名/密码/用户ID/组ID/描述信息/HOME目录/执行终端

5. getent group 查看系统全部组信息  组名称/组认证/组ID

## 1.3用户权限

![image-20230714173650289](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230714173650289.png)

![image-20230714173801348](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230714173801348.png)

ls -l 列出权限信息 

## 1.4 chmod 命令

![](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230714181502240.png)、

## 1.5 chown命令

![image-20230714183214483](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230714183214483.png)

# 3 . 实用操作

##  3.1 快捷操作 

ctrl + c 强制停止 

ctrl + d 退出，登出 ， 但是 vim 下 不能使用 

history 历史命令 

history | grep ch  过滤出带有 ch命令

!命令前缀 ， 自动执行上次带有此命令前缀的指令   !p  --> python  (之前输入过python指令)

ctrl + r  输入内容  匹配历史命令 

![image-20230714185352305](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230714185352305.png)

![image-20230714185727490](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230714185727490.png)

## 3.2 systemctl 控制 

systemctl start httpd 

yum install htppd

![image-20230715062049270](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230715062049270.png)

## 3.3 软连接 

![image-20230715063619398](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230715063619398.png)

## 3.4 时间校准

![image-20230715070249374](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230715070249374.png)

## 3.5 端口 

nmap IP地址 ， 查看制定IP的对外暴露接口

netstat -anp | grep 端口号 ， 查看本机指定端口号的占用情况 

## 3.6 进程管理

 ps -ef 查看进程信息

ps -ef | grep 关键字  ，过滤指定关键字的进程信息

kill [-9] 进程号 关闭指定进程号的进程

## 3.7 主机状态监控

1. 使用top命令   ： 任务管理器 ， CPU ， 内存 ，进程的信息
2. ​       df              ：  查看磁盘使用率
3. ​     iostat         ：  查看磁盘速率
4.  sar -n DEV  : 查看网络情况

## 3.8 环境变量 

一组信息记录 ， key-value类型 ，  

通过env命令查看 ， 通过$符号取出值

PATH , 修改环境变量 ， export 名称 = 值  临时生效 

永久生效 ： 

![image-20230715200240076](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230715200240076.png)

## 3.9 上传和下载 

![image-20230715201119380](C:\Users\xz\AppData\Roaming\Typora\typora-user-images\image-20230715201119380.png)

##  3.99  压缩和解压 

