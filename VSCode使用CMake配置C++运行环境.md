### VSCode使用CMake配置C++运行环境

1. VSCode 安装，VSCode插件安装（C/C++、CMake CMakeTools）

2. settings.json中只要null的那个选项的

3. 下面选择no activate kit处，选择unspcificed即可

4. 工程结构

   ``` 
   ├── bin（可执行文件，不用手动创建）
   │   └──
   ├── build（make文件，手动创建）
   │   ├── CMakeCache.txt
   ...
   ├── CMakeLists.txt(CMakeLists.txt自己编写)
   ├── include（头文件，自己创建）
   │   ├── a.h
   ...
   ├── LaneDetect_main.cpp（main文件，如果main文件包含在src中，camkelists.txt里面就可以只添加src，不用额外加main.cpp，手动编写）
   └── src(cpp文件，手动创建)
       ├── a.cpp
   	...
   
   ```

   

5. CMakeLists.txt内容

   ``` cmake
   cmake_minimum_required (VERSION 2.8)
   
   set(PROJECT_NAME LaneDetect)  # 最后生成的可执行文件名(damo)可更改
   
   project(LaneDetect0527)
   
   set(CMAKE_CXX_COMPILER "g++")
   set (CMAKE_CXX_FLAGS  "-g  -fexec-charset=GBK")
   set(EXECUTABLE_OUTPUT_PATH  ${PROJECT_SOURCE_DIR}/bin)
   
   
   find_package(OpenCV REQUIRED)
   
   #包含头文件
   include_directories(${PROJECT_SOURCE_DIR}/include)	#改成绝对路径也可以
   include_directories(/usr/local/include)
   
   # 包含cpp文件src里面的所有SrcFiles
   aux_source_directory(./src SrcFiles)
   
   #add executable file，添加要编译的可执行文件，要包括所有的Cpp文件
   add_executable(${PROJECT_NAME} ${SrcFiles} LaneDetect_main.cpp)
   
   
   #add link library，添加可执行文件所需要的库，
   TARGET_LINK_LIBRARIES(${PROJECT_NAME} ${OpenCV_LIBS})
   ```





