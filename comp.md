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
添加的文件夹；
原本的shared目录跟designer目录是平级的。
（ 原本 designer 和 shared 都位于 *Qt\Qt5.14.2\5.14.2\Src\qttools\src* ）
应该是要在多个项目中共用。designer用到了其中的一部分，所以装进来了。


shared包含一些子文件夹，测试后发现有些子文件不需要。删了
原始的子文件夹包括：
- corecon （删了
- deviceskin
- findwidget
- fontpanel
- qtgradienteditor
- qtpropertybrowser
- qttoolbardialog
- winutils（删了

列出子文件夹实现的功能
- deviceskin
  

#### findwidget
abstractfindwedget.h    
头文件定义了 AbstractFindWidget 抽象基类。AbstractFindWidget 是 Qwidget 的一个子类。
abstractfindwedget.cpp  
源文件实现了 AbstractFindWidget 

itemviewfindwidget.h    
头文件定义 ItemViewFindWidget 类。是 AbstractFindWidget 的一个子类。
itemviewfindwidget.cpp  
源文件实现 ItemViewFindWidget 类。

texteditfindwidget.h
头文件定义 TextEditFindWidget 类。是 AbstractFindWidget 的一个子类。
texteditfindwidget.cpp
源文件实现 TextEditFindWidget 类。

实现
### src\
原有的文件夹；
关于src文件夹内容多，单独列出文档。请参考 src-read.md 文档

### tests
添加的文件夹 desinger项目只依赖其中的 CmakeLists.txt 
