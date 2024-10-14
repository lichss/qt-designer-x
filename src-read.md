## src 文件夹说明

<!-- 比较重要的文件夹应该是 lib components designer -->

src文件夹的依赖关系，


- designer 依赖 components ，components依赖lib ，lib依赖uiplugin
    

plugins 依赖 lib

### lib文件夹
lib文件夹包含子文件夹：
  - components
  - extension
  - sdk
  - shared
  - uilib
和一个预编译头文件。**lib_pch.h**

分别说明各个子文件的作用：
<!-- 在这里添加分割！！ -->


- **lib/components文件夹**
包含两个头文件
**qdesigner_components.h** 和 **qdesigner_components_global.h**

    一个QDesignerComponents类提供声明，一个提供编译动态库时所需的导入导出符号。
    只有类声明。
    QDesignerComponents类在 src/components/lib/qdesigner_components.cpp 中实现
<!--lib包含了一些子模块、SDK、共享资源和项目配置文件。-->
-----------
- **lib/extension 文件夹**
提供 QExtensionFactory 、 QExtensionManager 这两个类。
声明，实现，动态库的导入导出宏都在这个文件。


<!-- sdk 文件夹 和 shared文件夹类似，都是头文件加源文件。 -->
----------
- **lib/shared 文件夹**
    包含一堆抽类的声明和实现。
    包含了一些通用的、共享的代码。
    这些代码在整个项目中被多个模块或组件所共用
-----------
- **lib/sdk 文件夹**
    包含一堆抽象基类的声明和实现。
    包含了一些与特定平台或SDK相关的代码。
-----------
- **lib/uilib 文件夹**
    提供了一些类。
    uilib 文件夹中的内容主要为 Qt Designer 提供了对用户界面元素的创建、组织、属性设置、资源管理、文本处理等功能的支持。
    其中 [QFormBuilder](designer/src/lib/uilib/formbuilder.h) 类应该比较重要。
    分了三个文件写的。
-----------
    
### components文件夹

components/lib 文件夹下
的预编译头文件lib_pch.h 包含了很多内容
`#include <QtDesigner/QtDesigner>`
QtDesigner/QtDesigner 指的是 include文件夹下的 QtDesigner 子文件夹下的 QtDesigner 文件
这个文件又包含了lib（designer/src/lib） 文件夹下的头文件
所以 components依赖lib

`#include <QtDesigner/qextensionmanager.h>`
指的是 src/lib/extension/qextensionmanager.h



除了lib文件夹外，其余buddyeditor 、 formeditor 、objecinspector、widgetbox、taskmenud都是包含了对应组件的源代码。
<!--我认为 shared文件夹下提供的那些组件应该和这些是平级的-->

### designer文件夹
**main.c在这个文件夹下**
designer文件夹下的源码调用components文件夹下的组件。
这里的源码应该主要处理用户界面和交互逻辑。
src.pro下的



### plugins

包含几个子文件夹，跟插件有关。什么ActiveQt、Qt Quick Widgers、 Qt WebKit

<!--在.pro文件中有设置，
如果不使用动态链接库编译，则不包含这个文件夹。
（默认使用动态链接库编译）-->

### uiplugin文件夹
<!-- uiplugin 是最低级依赖 -->

文件不多，两个头文件。一个是 customwidget.h ，另一个是 qdesignerexportwidget.h
这个文件夹只有头文件，没有源文件
customwidget.h 
定义了2个接口类.

QDesignerCustomWidgetInterface
QDesignerCustomWidgetCollectionInterface
<!-- 在哪实现的呢？ 。。。至少在repo 里找不到 -->



#### qdesignerexportwidget.h
这个头文件主要用于定义导出动态库的宏 QDESIGNER_WIDGET_EXPORT
<!--这样的宏在其他源文件中非常常见-->

### uitools文件夹
uitools文件夹提供QUiloader 类。
QUiloader 类主要用于从Qt Designer生成的.ui文件加载UI界面。
**quiloader_p.h**
包含 QUiLoader 类的一些私有成员变量和函数。
**quiloader.h** 
QUiLoader类的公共头文件，公开了类的所有公共接口，以及其他对外提供的方法。
**quiloader.cpp**
包含具体实现。