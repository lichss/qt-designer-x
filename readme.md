### 第一次提交
原文件夹designer直接复制出来不能工作。

qmake编译报错: 
    " 'qtNomakeTools' is not a recognized test function. "
    Project ERROR: Module does not define version.


### 第二次提交
添加文件 .qmake.conf .qmake.stash configure.json symc.profile 后qamke通过。
现在qmake提示 缺少xxxx.pri文件

### 第三次提交
添加 shared\ 文件夹到:\designer，（源自 :\Qt\Qt5.14.2\5.14.2\Src\qttools\src） 注意和 :\designer\src\lib 文件夹下的shared\区别。

#### 修改 pro & pri文件：
    修改designer\src\lib\shared.pri                                 第10 - 20 行。更正相对路径
    修改designer\src\component\propertyeditor\propertyeditor.pri        第5-11行。更正相对路径
    修改designer\src\component\objectinspector\objectinspector.pri        第3-7行。更正相对路径
    修改designer\src\designer\src\designer\designer.pro                 第16-17行。更正相对路径

修改后qmake生成Makefile应该不报错也不报警告。能正常生成


### 第四次提交
添加shared文件夹


