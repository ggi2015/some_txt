## caffe 安装
参考安装[例程](https://blog.csdn.net/CAU_Ayao/article/details/83536320#1__18)  
期间遇到`caffe: error while loading shared libraries: libcudart.so.10.0: cannot open shared object file: No such file or directory` ，[解决](https://blog.csdn.net/quantum7/article/details/88848565)  

在`python` 中 `import caffe`   
出现：`ImportError: libpython3.6m.so.1.0: cannot open shared object file: No such file or directory` ，[解决](https://blog.csdn.net/weixin_43952432/article/details/100077912)  
出现：`RuntimeError: module compiled against API version 0xc but this version of numpy is 0xb` ,[解决](https://blog.csdn.net/lzjstudy/article/details/87898663)  
出现：`ModuleNotFoundError: No module named 'google'` ，[解决](https://blog.csdn.net/weixin_36670529/article/details/111351520)  
出现：[` ERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
pandas 1.1.5 requires python-dateutil>=2.7.3, but you have python-dateutil 1.5 which is incompatible.
matplotlib 3.3.4 requires python-dateutil>=2.1, but you have python-dateutil 1.5 which is incompatible.`]， [解决](https://blog.csdn.net/CAU_Ayao/article/details/83538024)   
出现：[`.build_release/tools/caffe: error while loading shared libraries: libcudart.so.10.0: cannot open shared object file: No such file or directory
Makefile:542: recipe for target 'runtest' failed
make: *** [runtest] Error 127`]，[解决1](https://blog.csdn.net/CAU_Ayao/article/details/83538794),要是解决1不行，[解决2](https://blog.csdn.net/weixin_43439673/article/details/84198164); 我第一次可以用解决1解决，但是第二次却用的解决2才可以；  

## todo
目前遇到问题，在python中，`import caffe`，显示 `ModuleNotFoundError: No module named 'numpy.core._multiarray_umath` ; 尝试更新numpy版本，但是又会出现 `0x0e与0x0d`的问题；降低numpy版本，出现依赖版本要求不满足的问题； 
