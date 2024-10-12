## src 文件夹说明

比较重要的文件夹应该是 lib components designer

src文件夹的依赖关系，
lib 依赖 uiplugin
components 依赖 lib
designer 依赖 components

plugins 依赖 lib



### uiplugin文件夹
<!-- uiplugin 是最低级依赖 -->

文件不多，两个头文件。一个是 customwidget.h ，另一个是 qdesignerexportwidget.h
这个文件夹只有头文件，没有源文件
#### customwidget.h 
定义了2个基类.

QDesignerCustomWidgetInterface
QDesignerCustomWidgetCollectionInterface
<!-- 在哪实现的呢？ 。。。 -->

<!-- 包含一些基本方法。 -->

#### qdesignerexportwidget.h
这个头文件主要用于定义导出动态库的宏 QDESIGNER_WIDGET_EXPORT
<!--这个宏在其他源文件中非常常见-->

### uitools文件夹
uitools文件夹提供QUiloader 类。
QUiloader 类主要用于从Qt Designer生成的.ui文件加载UI界面。
**quiloader_p.h**
包含 QUiLoader 类的一些私有成员变量和函数。
**quiloader.h** 
QUiLoader类的公共头文件，公开了类的所有公共接口，以及其他对外提供的方法。
**quiloader.cpp**
包含具体实现。

- designer 依赖 components ，components依赖lib 。
    其中components包含各类组件。
### lib文件夹
<!-- lib、components、designer文件夹层次明显 -->

lib/components文件夹
两个头文件
**qdesigner_components.h** 和 **qdesigner_components_global.h**

一个QDesignerComponents类提供声明，一个提供编译动态库时所需的导入导出符号。

QDesignerComponents类在 src/components/lib/qdesigner_components.cpp 中实现
<!--lib包含了一些子模块、SDK、共享资源和项目配置文件。-->

lib/extension 文件夹
提供 QExtensionFactory 、 QExtensionManager 这两个类。
声明，实现，动态库的导入导出宏都在这个文件。

*文件很多*



### components文件夹
包含了designer项目的组件的源代码。components 依赖于lib 
components 文件夹下还有一个lib文件夹，只包含lib_pch.h 头文件 和 qdesigner_components.cpp 源文件。
应该是用来初始化各个组件。

除了lib文件夹外，其余buddyeditor 、 formeditor 、objecinspector、widgetbox、taskmenud都是包含了对应组件的源代码。


### designer文件夹
designer文件夹下的源码调用components文件夹下的组件。
src.pro下的





### plugins
如果不使用动态链接库编译，则不需要这个文件夹。（默认使用动态链接库编译）