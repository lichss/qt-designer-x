### data\
原有的文件夹；包含一些xsl、xsd文件
与自动生成cpp代码有关。文件夹中有[READMD](./designer/data/README)文件。


### include\
添加的文件夹；
原本include 文件夹所在的位置比designer文件夹高一级
- include文件夹位于： \Qt\Qt5.14.2\5.14.2\Src\qttools
- designer文件夹位于： \Qt\Qt5.14.2\5.14.2\Src\qttools\src\
  
添加include文件夹的是因为designer项目中有些源文件包含了include文件夹下的一些头文件。
为了designer切出来还能用，把include文件夹添加进designer项目下。

include 文件夹内包含了很多只含有一行相对路径的头文件。

`#include "../../designer/src/lib/sdk/abstractactioneditor.h"`

只要包含了include文件夹下的头文件就相当于包含了同名的头文件。
这些同名头文件都位于 designer/src/lib 文件夹下。


### shared\ 
添加的文件夹；
shared文件夹详细内容参考 [shared-read.md](./shared-read.md)


### src\
原有的文件夹；
关于src文件夹内容多，单独列出文档。参考 [src-read.md](./src-read.md) 文档

### tests
添加的文件夹.
子文件夹很多，只含有一个文件。[CmakeLists.txt](./designer/tests/auto/cmake/CMakeLists.txt)
文件中有注释提到这个文件用于测试

