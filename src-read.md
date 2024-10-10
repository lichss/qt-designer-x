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

#### customwidget.h 
定义了2个基类.

QDesignerCustomWidgetInterface
QDesignerCustomWidgetCollectionInterface
<!-- 包含一些基本方法。 -->

#### qdesignerexportwidget.h
这个头文件主要用于定义导出动态库的宏 QDESIGNER_WIDGET_EXPORT
这个宏在其他源文件中非常常见

### uitools文件夹
包含头文件，源文件 还有一个子目录
提供QUiLoader 类

- designer 依赖 components ，components依赖lib 。
    其中components包含各类组件。
### lib文件夹
<!-- lib、components、designer文件夹层次明显 -->

lib包含了一些子模块、SDK、共享资源和项目配置文件。
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