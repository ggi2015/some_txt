## Linux系统下，U盘只读文件系统问题解决

问题描述：Ubuntu插入U盘为只读文件系统,无法新建文件,文件夹或者向U盘中复制文件

问题解决：

1. 插入U盘并用df -h查看U盘信息: 

    ```
   df -h 
   可得，U盘文件系统为/dev/sdb5，挂载点为/media/zoutao/disk
    ```

2. ​	 卸载U盘

   ```
   sudo umount /media/zoutao/disk1
   卸载之后一定不能拔掉U盘
   ```

3. 修复U盘文件系统故障

   ```
   sudo dosfsck -v -a /dev/sdb5
   ```

4. 重新挂载U盘即可解决. (拔了再插)

