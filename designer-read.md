### data\
原有的文件夹；包含一些xsl、xsd文件
与自动生成cpp代码有关。文件夹中有readme文件。


### include\
添加的文件夹；
原本include 文件夹所在的位置比designer文件夹高一级
- include文件夹位于： \Qt\Qt5.14.2\5.14.2\Src\qttools
- designer文件夹位于： \Qt\Qt5.14.2\5.14.2\Src\qttools\src\
  
添加include文件夹的是因为designer项目中有些源文件包含了include文件夹下的一些头文件。
为了designer切出来还能用，把include文件夹添加进designer项目下。
<!-- 他妈的 include文件夹和 src/lib文件夹有联动 -->
include 文件夹内包含了很多只含有一行相对路径的头文件。
只要包含了include文件夹下的头文件就相当于包含了同名的头文件。
这些同名头文件都位于 designer/src/lib 文件夹下。
<!--有点想不明白为啥这样搞。可能是为了开发的方便吧。
写在.pri .pro 文件里方便点？


包含头文件时总是去包含include文件夹下的头文件。-->


### shared\ 
shared文件夹详细内容参考 [shared-read.md](shared-read.md)


### src\
原有的文件夹；
关于src文件夹内容多，单独列出文档。参考 [src-read.md](src-read.md) 文档

### tests
添加的文件夹 desinger项目只依赖其中的 CmakeLists.txt 
