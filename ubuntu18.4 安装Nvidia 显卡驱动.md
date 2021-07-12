`ubuntu18.4` 安装`Nvidia` 显卡驱动

[主教程](
https://blog.csdn.net/new_delete_/article/details/81544438)

期间遇到:
`dpkg-divert: error: mismatch on package`
 ` when removing 'diversion of /usr/lib/x86_64-linux-gnu/libGL.so.1 by libnvidia-gl-450'
  found 'diversion of /usr/lib/x86_64-linux-gnu/libGL.so.1 to /usr/lib/x86_64-linux-gnu/libGL.so.1.distrib by nvidia-340'`
[解决办法](
https://qastack.cn/ubuntu/1035409/installing-nvidia-drivers-on-18-04)
关键命令:
`LC_MESSAGES=C dpkg-divert --list '*nvidia-340*' | sed -nre 's/^diversion of (.*) to .*/\1/p' | xargs -rd'\n' -n1 -- sudo dpkg-divert --remove`
`sudo apt --fix-broken install`

显卡驱动下载：
[https://www.nvidia.com/en-us/geforce/drivers/] 
cuda下载：
[https://developer.nvidia.com/cuda-toolkit-archive]
cudnn下载：
[https://developer.nvidia.com/rdp/cudnn-archive]
（建议配合教程食用（上网上搜））

 
[cuda100版本的pytorch]( pip install torch==1.4.0+cu100 torchvision==0.5.0+cu100 -f https://download.pytorch.org/whl/torch_stable.html)  
[tf115](pip install tensorflow-gpu==1.15)  

