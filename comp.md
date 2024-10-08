### data\
原有的文件夹；包含一些xsl、xsd文件
与自动生成cpp代码有关。文件夹中有readme文件。


### include\
添加的文件夹；designer项目中有些源文件包含了include文件夹下的一些头文件。为了designer切出来还能用，把include文件夹添加进designer项目下。

### shared\ 
添加的文件夹；包含多个子文件夹。原本存在于  qttools/  文件夹下.在qttools下的多个项目中共用。
原始的子文件夹包括：
corecon
deviceskin
findwidget
fontpanel
qtgradienteditor
qtpropertybrowser
qttoolbardialog
winutils
其中corecon、winutil不被designer依赖。删了

### src\
原有的文件夹；


### tests
添加的文件夹 desinger项目只依赖其中的 CmakeLists.txt 
