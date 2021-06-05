### electron-ssr安装配置和终端翻墙

安装electron-ssr

[工欲善其事必先利其器](https://www.jianshu.com/p/fba8637da1e3)

[客户端下载地址](https://github.com/qingshuisiyuan/electron-ssr-backup/releases/download/v0.2.6/electron-ssr-0.2.6.deb)

安装依赖：

```
sudo apt install libcanberra-gtk-module libcanberra-gtk3-module gconf2 gconf-service libappindicator1
```

可选依赖（如果软件报错，请安装可选依赖，都安装也没问题）

``` 
sudo apt-get install libssl-dev 
sudo apt-get install libsodium-dev
```



安装：

```
sudo dpkg -i electron-ssr-0.2.6.deb
```



2. 运行

   ``` 
   electron-ssr
   ```

   运行需要python

   ``` 
   sudo apt install python
   ```

3. 添加飞机

   可以先试试在订阅管理中，添加订阅（我无法添加）

   故，单个添加飞机（请务必确保单个添加的是可用的，否则会误判为软件不行。美国p1s可）

   在系统设置->网络设置->网络代理设置中，选择自动，其中`configuration URL` 会自动填入`http://127.0.0.1:2333/proxy.pac` (无需手填，看一下就好）

4. 完成上述步骤之后，打开浏览器，`google.com` 等网站就可访问了

5. 终端翻墙

   百度搜索 终端 翻墙，得到[终端翻墙备忘录](https://andrewpqc.github.io/2018/04/30/let-the-terminal-penetrate-the-firewall/)

   命令合集：

   ```
   - 安装
   sudo apt-get install privoxy
   - 配置
   在/etc/privoxy/config文件中添加如下的一条配置：
   forward-socks5 / 127.0.0.1:1080 .
   - 重启provixy服务，并确认已经启动
   service privoxy restart
   service privoxy status
   privoxy服务默认跑在本地的8118端口。
   
   
   - 安装
   sudo apt-get install polipo
   - 配置
   在/etc/polipo/config文件中做如下的配置：
   # This file only needs to list configuration variables that deviate
   # from the default values.  See /usr/share/doc/polipo/examples/config.sample
   # and "polipo -v" for variables you can tweak and further information.
   
   logSyslog = true
   logFile = /var/log/polipo/polipo.log
   
   proxyAddress = "0.0.0.0"
   
   socksParentProxy = "127.0.0.1:1080"
   socksProxyType = socks5
   
   chunkHighMark = 50331648
   objectHighMark = 16384
   
   dnsQueryIPv6 = no
   - 重启并确认
   service polipo restart
   service polipo status
   polipo服务默认跑在本地的8123端口。
   
   - 终端设置
   	- 当前终端设置代理
   	export http_proxy=`http://127.0.0.1:8118`
   	export https_proxy='http://127.0.0.1:8118'
   	在.bashrc文件中设置代理
   	alias proxy="export http_proxy=http://localhost:8118;export https_proxy=http://localhost:8118" 
   	alias unproxy="unset http_proxy;unset https_proxy"
   	- 生效配置
   	source .bashrc
   
   -终端启动代理或者终止代理
   	proxy	unproxy
   	
   
   
   ```

   



​	

​			















无法添加muyun订阅



autoware setup (https://github.com/Autoware-AI/autoware.ai/wiki/Source-Build) 

