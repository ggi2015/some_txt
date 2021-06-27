#ubuntu18.04 更新（内核）之后，NVIDIA显示如下问题：

``` 
NVIDIA-SMI has failed because it couldn't communicate with the NVIDIA driver. Make sure that the latest NVIDIA driver is installed and running.

```

解决办法:

[https://zhuanlan.zhihu.com/p/89714824]

``` bash
网页上说，是更新了内核之后，以前安装的显卡驱动并没有带过来，所以以前可用的显卡驱动就不能用了；
sudo apt install dkms
sudo dkms install -m nvidia -v 418.87.00

其中，418.87.00 是之前安装 nvidia 驱动的版本号，可通过下面方法查到：
ls /usr/src | grep nvidia
```

