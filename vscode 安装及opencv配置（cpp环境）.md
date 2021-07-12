vscode 安装及opencv配置（cpp环境）

1. vscode install
2. gcc\g++\gdb install 
3. opencv 配置
   1. 参考[网站](https://blog.csdn.net/u012704941/article/details/80396249)
   2. 具体步骤
      1. [opencv](https://github.com/opencv) 在`code` 选项中，选择`tag` ，再选择`release` ，下载源码和`contrib` 源码
      2. [安装配置opencv](https://blog.csdn.net/bryan_qaq/article/details/90246739)，要是在`Cmakeerrorlog` 中有`    Regex: 'argument .* is not valid'`  的报错，将`OPENCV_EXTRA_MODULES_PATH` 改成绝对路径试试；过程中会联网下载东西，可以提前把梯子挂上，但是不一定有用；
      3. make and other option [website](https://blog.csdn.net/weixin_44436677/article/details/105586820)
4. vscode 配置
   1. 安装`c/c++` 插件；
   2. 打开`opencv` 测试代码
   3. `c++` 配置

