#########
原文件夹designer直接复制出来不能工作。
qmake编译报错: 
    " 'qtNomakeTools' is not a recognized test function. "
    Project ERROR: Module does not define version.
#########
添加文件 .qmake.conf .qmake.stash configure.json symc.profile 后qamke通过。
现在qmake提示 缺少xxxx.pri文件
