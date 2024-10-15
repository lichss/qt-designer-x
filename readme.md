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
    修改designer\src\lib\shared.pri                                  第10 - 20 行。更正相对路径
    修改designer\src\component\propertyeditor\propertyeditor.pri         第5-11行。更正相对路径
    修改designer\src\component\objectinspector\objectinspector.pri        第3-7行。更正相对路径
    修改designer\src\designer\src\designer\designer.pro                 第16-17行。更正相对路径

修改后qmake生成Makefile应该不报错也不报警告。能正常生成


### 第四次提交
添加shared文件夹

### 第五次提交
添加外部依赖 /include 文件夹到项目下
* /include 文件夹来自 : \Qt\Qt5.14.2\5.14.2\Src\qttools\ 

#### 修改 .h 头文件
    以下头文件改了相对路径。原先的上级目录有变化了。
    这些头文件都是只有一行，用来include其他头文件。
    modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/abstractdialoggui_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/abstractintrospection_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/actioneditor_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/actionprovider_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/actionrepository_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/codedialog_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/connectionedit_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/csshighlighter_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/deviceprofile_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/dialoggui_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/extensionfactory_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/formbuilderextra_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/formlayoutmenu_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/formwindowbase_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/grid_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/gridpanel_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/htmlhighlighter_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/iconloader_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/iconselector_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/invisible_widget_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/layout_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/layoutinfo_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/lib_pch.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/metadatabase_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/morphmenu_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/newactiondialog_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/newformwidget_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/orderdialog_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/plaintexteditor_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/plugindialog_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/pluginmanager_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/previewconfigurationwidget_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/previewmanager_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/promotionmodel_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/promotiontaskmenu_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/properties_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/propertylineedit_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_command2_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_command_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_dnditem_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_dockwidget_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_formbuilder_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_formeditorcommand_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_formwindowcommand_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_formwindowmanager_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_introspection_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_membersheet_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_menu_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_menubar_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_objectinspector_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_promotion_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_promotiondialog_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_propertycommand_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_propertyeditor_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_propertysheet_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_qsettings_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_stackedbox_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_tabwidget_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_taskmenu_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_toolbar_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_toolbox_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_utils_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_widget_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_widgetbox_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qdesigner_widgetitem_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qlayout_widget_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qsimpleresource_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qtresourceeditordialog_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qtresourcemodel_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/qtresourceview_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/rcc_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/resourcebuilder_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/richtexteditor_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/selectsignaldialog_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/shared_enums_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/shared_global_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/shared_settings_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/sheet_delegate_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/signalslotdialog_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/spacer_widget_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/stylesheeteditor_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/textbuilder_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/textpropertyeditor_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/ui4_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/widgetdatabase_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/widgetfactory_p.h
	modified:   designer/include/QtDesigner/5.14.2/QtDesigner/private/zoomwidget_p.h
	modified:   designer/include/QtDesigner/abstractactioneditor.h
	modified:   designer/include/QtDesigner/abstractdnditem.h
	modified:   designer/include/QtDesigner/abstractformbuilder.h
	modified:   designer/include/QtDesigner/abstractformeditor.h
	modified:   designer/include/QtDesigner/abstractformeditorplugin.h
	modified:   designer/include/QtDesigner/abstractformwindow.h
	modified:   designer/include/QtDesigner/abstractformwindowcursor.h
	modified:   designer/include/QtDesigner/abstractformwindowmanager.h
	modified:   designer/include/QtDesigner/abstractformwindowtool.h
	modified:   designer/include/QtDesigner/abstractintegration.h
	modified:   designer/include/QtDesigner/abstractlanguage.h
	modified:   designer/include/QtDesigner/abstractmetadatabase.h
	modified:   designer/include/QtDesigner/abstractnewformwidget.h
	modified:   designer/include/QtDesigner/abstractobjectinspector.h
	modified:   designer/include/QtDesigner/abstractoptionspage.h
	modified:   designer/include/QtDesigner/abstractpromotioninterface.h
	modified:   designer/include/QtDesigner/abstractpropertyeditor.h
	modified:   designer/include/QtDesigner/abstractresourcebrowser.h
	modified:   designer/include/QtDesigner/abstractsettings.h
	modified:   designer/include/QtDesigner/abstractwidgetbox.h
	modified:   designer/include/QtDesigner/abstractwidgetdatabase.h
	modified:   designer/include/QtDesigner/abstractwidgetfactory.h
	modified:   designer/include/QtDesigner/container.h
	modified:   designer/include/QtDesigner/default_extensionfactory.h
	modified:   designer/include/QtDesigner/dynamicpropertysheet.h
	modified:   designer/include/QtDesigner/extension.h
	modified:   designer/include/QtDesigner/extension_global.h
	modified:   designer/include/QtDesigner/extrainfo.h
	modified:   designer/include/QtDesigner/formbuilder.h
	modified:   designer/include/QtDesigner/layoutdecoration.h
	modified:   designer/include/QtDesigner/membersheet.h
	modified:   designer/include/QtDesigner/propertysheet.h
	modified:   designer/include/QtDesigner/qdesigner_components.h
	modified:   designer/include/QtDesigner/qdesigner_components_global.h
	modified:   designer/include/QtDesigner/qextensionmanager.h
	modified:   designer/include/QtDesigner/sdk_global.h
	modified:   designer/include/QtDesigner/taskmenu.h
	modified:   designer/include/QtDesigner/uilib_global.h
	modified:   designer/include/QtUiPlugin/customwidget.h
	modified:   designer/include/QtUiPlugin/qdesignerexportwidget.h

删除一些文件。
- deleted:    designer/sync.profile
- deleted:    designer/.qmake.stash
- deleted:    designer/configure.json

### 第7次提交
删除文件夹： 
- include/QtDesignerComponents
- include/QtHelp
- include/QtUiPlugin
- include/QtUiTools
- shared/coreon
- shared/winutils
