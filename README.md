关于SSR应该很多人都不陌生。SSR其实是SS的升级版。接下来我要说的就是如何搭建SSR的服务器。

最下方有SSR客户端的下载链接,百度网盘可直接下载

# 一.购买服务器，或者准备一台服务器
#### （一）注意：
1. 这一台服务器必须处于公网，拥有公网IP
2. 这一台服务器必须可以访问外网（你知道为什么）
3.这一台服务器系统是Ubuntu或者CentOS系统（只要是Linux应该都行，但是我只会这两种系统的一些基础）
#### （二）如何购买服务器
这个我就不想多说了。服务器购买有一大把。我用的是阿里云香港服务器。
##### 关于阿里云服务器的一些注意：
###### 1. 安全规则配置。
因为我第一次使用阿里云。所以第一次配置的时候没有成功还以为是配置错了。折腾了两天才发现原来是设置了安全规则过滤了外网对其的访问。
###### 2. 没有更多了了
# 二. 配置服务器
### Ubuntu:
##### 安装 wget,如果服务器本身已经安装了wget可以跳过这一步
Ubuntu 16以上
```terminal
apt install wget
```
Ubuntu 16之前
```terminal
apt-get install wget
```
CentOS
```terminal
yum -y install wget
```
#####安装ssr配置脚本

```terminal
wget -N --no-check-certificate https://softs.fun/Bash/ssr.sh
chmod +x ssr.sh
bash ssr.sh
```
#####备用地址

```terminal
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh
chmod +x ssr.sh
bash ssr.sh
```
上方命令执行完毕之后效果应该是这样的：

![image.png](http://upload-images.jianshu.io/upload_images/6245842-c61be6d239fd67b8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
接下来按照脚本提示输入对应的编号就可以了。
##### 安装SSR
根据提示，安装SSR，输入1

![image.png](http://upload-images.jianshu.io/upload_images/6245842-60fd159675c8042b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##### 设置SSR服务器的端口
这个端口用于SSR客户端与SSR服务器建立链接的时候使用。默认2333.在这里我直接使用默认（直接敲回车）

![image.png](http://upload-images.jianshu.io/upload_images/6245842-66b14c7d81e6ded1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置SSR链接时候的密码。
这里我设置的是1234

![image.png](http://upload-images.jianshu.io/upload_images/6245842-5cba2d1cd6acd98e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置加密方式
这里我为了能兼容SS，加密方式我选择的是3

![image.png](http://upload-images.jianshu.io/upload_images/6245842-18f33a5b3fac95ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置协议插件
同样为了兼容SS，我选择了1

![image.png](http://upload-images.jianshu.io/upload_images/6245842-ee8e3943d44afb5d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置混淆插件
同样为了兼容SS，我选择了1

![image.png](http://upload-images.jianshu.io/upload_images/6245842-de7bbcd207d35201.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 限制登陆设备个数
我不需要限制，所以直接回车

![image.png](http://upload-images.jianshu.io/upload_images/6245842-8c0fac4bca1c8a78.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置单个端口限速
不需要，直接回车

![image.png](http://upload-images.jianshu.io/upload_images/6245842-ae7fe036f74bca1d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 设置端口限速（所有端口的总速度，多端口模式下更能体现，个人使用一般是单端口，不需要理会）
不需要，直接回车

![image.png](http://upload-images.jianshu.io/upload_images/6245842-b11c869d20319366.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这个回车之后就会有一大堆乱七八糟的东西，等一等，让它自己配置。结束之后如图：

![image.png](http://upload-images.jianshu.io/upload_images/6245842-a0f12abc144bf3ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
为了保密，我把IP，SS和SSR链接P掉了。毕竟我的服务器只是一个很小的服务器，不敢拿出来共享。在此说一声抱歉。
# 三.配置加速
这一步其实可以不要。但是为了从此之后不再忧心与SSR服务器的重启（服务器重启后SSR服务会被关闭，需要重新手动启动）和SSR代理网络速度更快，推荐大家往下看。
##### 安装谷歌BBR加速
```terminal
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
chmod +x bbr.sh
./bbr.sh
```
把上述的代码依次执行一遍，执行完之后是这样的

![image.png](http://upload-images.jianshu.io/upload_images/6245842-efa9703df1b9363b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这事只需要按一下键盘上任意一个按键即可（按一下就行，不需要多按，等一下就会有反应了）
等安装完之后是这样的

![image.png](http://upload-images.jianshu.io/upload_images/6245842-5bf4cb40ea037fa8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这里是在询问是否重启系统。我们输入y.回车之后会发现已经与服务器断开链接了。不必担心，这是服务器在重启。等一下再次连接即可。
如果想再次配置SSR，只需要输入命令
```terminal
bash ssr.sh
```
就会重新回到安装的界面

![image.png](http://upload-images.jianshu.io/upload_images/6245842-e5b70e039cb0b0d5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
输入7即可根据需要自己修改配置了。怎么样，很简单吧。
不过服务器这东西一般人还是很难拥有的。感谢阅读。

SSR客户端百度网盘下载链接：[https://pan.baidu.com/s/1n4-bhlDaQH23RAY5u1HL2w](https://pan.baidu.com/s/1n4-bhlDaQH23RAY5u1HL2w)  密码:k8j4
