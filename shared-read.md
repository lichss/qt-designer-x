
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
- **deviceskin**
    deviceskin.h定义了DeviceSkin类 、 DeviceSkinParameters结构体 、 DeviceSkinButtonArea结构体。
    都在deviceskin.cpp中实现。



- **findwidget**
  
    abstractfindwedget.h    
    定义了 AbstractFindWidget 抽象基类。AbstractFindWidget 是 Qwidget 的一个子类。
    abstractfindwedget.cpp  
    源文件实现了 AbstractFindWidget 

    itemviewfindwidget.h    
    定义 ItemViewFindWidget 类。是 AbstractFindWidget 的一个子类。
    itemviewfindwidget.cpp  
    源文件实现 ItemViewFindWidget 类。

    texteditfindwidget.h
    头文件定义 TextEditFindWidget 类。是 AbstractFindWidget 的一个子类。
    texteditfindwidget.cpp
    源文件实现 TextEditFindWidget 类。

- **fontpanel**
    提供FontPanel类。
    fontpanel.h 声明 fontpanel.cpp 实现

- **qtgradienteditor**
    提供qtgradienteditor和相关的类。
    包含声明和实现。
    *QtGradientEditor 是 Qt自带的渐变色编辑工具*

- **qtpropertybrowser**
    提供qtgradienteditor和相关的类。
    包含声明和实现。
    *QtPropertyBrowser 是 Qt的属性表控件*

- **qttoolbardialog**
    提供 QtToolBarManager和 QtToolBarDialog类。
    包含声明和实现。
    *都是用来管理工具栏的*