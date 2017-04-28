![logo](http://oop4q34sz.bkt.clouddn.com/apicloud.png)

# APICloud-Modules


[UIInput](#uiinput "输入框模块，开发者可通过配置相应参数来控制输入框自动获取焦点，并弹出键盘。") [UIListView](#uilistview "可以侧滑滚动的列表模块") [UIChatBox](#uichatbox "聊天输入框模块")  [UIMediaScanner](#uimediascanner "本地媒体资源扫描器") [UIMultiSelector](#uimultiselector "支持多选的选择器") [UISearchBar](#uisearchbar "独立的搜索页面") [UICalendar](#uicalendar "日历选择模块") [UIPullRefresh](#uipullrefresh "下拉刷新模块") [NVTabBar](#nvtabbar "一个底部导航条模块") [FNScanner](#fnscanner "二维码/条形码扫描器") [imageFilter](#imagefilter "封装了对图片按照指定效果过滤的功能") [photoBrowser](#photobrowser "图片浏览器") [ble](#ble "蓝牙4.0模块") [pedometer](#pedometer "手机计步器模块") [aMap](#amap "高德地图模块") [bMap](#bmap "百度地图模块") 


## UIInput

一个输入框模块，开发者可通过配置相应参数来控制输入框自动获取焦点，并弹出键盘。

某些 App 具有打开某一页面即可默认弹出键盘的功能，如某些登陆授权、评论页面。但是一个纯 html 的输入框标签，无法实现这一功能。为满足 APICloud 平台开发者对这一功能的需求，特推出了 UIInput 模块。

UIInput 是一个输入框模块，开发者可通过配置相应参数来控制输入框自动获取焦点，并弹出键盘。同普通的 UI 类的模块一样，本模块也可通过 rect 来设置其位置和大小，通过 styles参数设置其样式。为增强输入框功能，模块开放了 keyboardType 参数，开发者可通过设置该参数来控制其键盘类型。

### 文档
[http://docs.apicloud.com/Client-API/UI-Layout/UIInput](http://docs.apicloud.com/Client-API/UI-Layout/UIInput)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/UIInput](#https://github.com/apicloudcom/UIInput)


## UIListView

一个可以侧滑滚动的列表模块

UIListView 模块封装了一个数据列表控件，列表项水平侧滑可出现控制按钮；开发者可自定义列表的数据源，及列表的样式，支持列表项的增、删、改、查，支持批量更新、追加数据，支持下拉刷新和上拉加载事件。UIListView 模块是 listView 模块的优化版。

### 文档
[http://docs.apicloud.com/Client-API/UI-Layout/UIListView](http://docs.apicloud.com/Client-API/UI-Layout/UIListView)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/UIListView](#https://github.com/apicloudcom/UIListView)


## UIChatBox

一个聊天输入框模块

UIChatBox 模块是一个聊天输入框模块，开发者可自定义该输入框的功能。通过 open 接口可在当前 window 底部打开一个输入框，该输入框的生命属于当前 window 所有。当输入框获取焦点后，会自动弹动到软键盘之上。开发者可通过监听输入框距离底部弹动的高度，来改变聊天对话界面的高度，从而实现类似 QQ 聊天页面的功能。UIChatBox 模块是 chatBox 模块的优化版。

### 文档
[http://docs.apicloud.com/Client-API/UI-Layout/UIChatBox](http://docs.apicloud.com/Client-API/UI-Layout/UIChatBox)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/UIChatBox](#https://github.com/apicloudcom/UIChatBox)


## UIMediaScanner

一个本地媒体资源扫描器

UIMediaScanner 是一个本地媒体资源扫描器，在 Android 平台上可扫描整个设备的资源，iOS 仅扫描相册内的资源。开发者可通过 open 内的 type 参数控制要扫描的资源类型。

### 文档
[http://docs.apicloud.com/Client-API/UI-Layout/UIMediaScanner](http://docs.apicloud.com/Client-API/UI-Layout/UIMediaScanner)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/UIMediaScanner](#https://github.com/apicloudcom/UIMediaScanner)


## UIMultiSelector

一个支持多选的选择器

UIMultiSelector 封装了一个支持多选的选择器，开发者可自定义该选择器的样式及其数据源。当您的 APP 需要为用户同时提供多种可选项的支持时可以选择该控件快速配置使用节省开发时间。该模块是 multiSelector 模块的优化版本

### 文档
[http://docs.apicloud.com/Client-API/UI-Layout/UIMultiSelector](http://docs.apicloud.com/Client-API/UI-Layout/UIMultiSelector)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/UIMultiSelector](#https://github.com/apicloudcom/UIMultiSelector)


## UISearchBar

一个独立的搜索页面，相当于打开一个 window 。

### 文档
[http://docs.apicloud.com/Client-API/UI-Layout/UISearchBar](http://docs.apicloud.com/Client-API/UI-Layout/UISearchBar)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/UISearchBar](#https://github.com/apicloudcom/UISearchBar)


## UICalendar

一个日历选择模块

UICalendar 是一个日历选择模块；可自定义日历的样式，添加特殊日期标注，切换月份，设置指定日期；用于实现常用的日期选择，日历展示功能。UICalendar 模块是 calendar 模块的优化版。

### 文档
[http://docs.apicloud.com/Client-API/UI-Layout/UICalendar](http://docs.apicloud.com/Client-API/UI-Layout/UICalendar)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/UICalendar](#https://github.com/apicloudcom/UICalendar)


## UIPullRefresh

下拉刷新模块

### 文档
[http://docs.apicloud.com/Client-API/UI-Layout/UIPullRefresh](http://docs.apicloud.com/Client-API/UI-Layout/UIPullRefresh)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/UIPullRefresh](#https://github.com/apicloudcom/UIPullRefresh)


## NVTabBar

一个底部导航条模块

NVTabBar 是一个底部导航条模块，该模块依附于当前主 window 。开发者可通过相应接口参数自定义其样式，设置、取消选中状态，动态配置 item 的徽章（badge）等功能。

### 文档
[http://docs.apicloud.com/Client-API/Nav-Menu/NVTabBar](http://docs.apicloud.com/Client-API/Nav-Menu/NVTabBar)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
<!-- - 开源地址：[https://github.com/apicloudcom/NVTabBar](#https://github.com/apicloudcom/NVTabBar) -->


## FNScanner

一个二维码/条形码扫描器

FNScanner 模块是一个二维码/条形码扫描器，是 scanner 模块的优化升级版。在 iOS 平台上本模块底层集成了系统自带扫码功能。

### 文档
[http://docs.apicloud.com/Client-API/Func-Ext/FNScanner](http://docs.apicloud.com/Client-API/Func-Ext/FNScanner)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/FNScanner](#https://github.com/apicloudcom/FNScanner)


## imageFilter

封装了对图片按照指定效果过滤的功能

imageFilter 模块封装了对图片按照指定效果过滤的功能，过滤后的图片可保存到指定目录。另外通过本模块的 getAttr 接口可获取制定图片的大小等信息，compress 接口可实现压缩图片的相关功能。

### 文档
[http://docs.apicloud.com/Client-API/Func-Ext/imageFilter](http://docs.apicloud.com/Client-API/Func-Ext/imageFilter)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/imageFilter](#https://github.com/apicloudcom/imageFilter)


## photoBrowser

一个图片浏览器

photoBrowser 是一个图片浏览器，支持单张、多张图片查看的功能，可放大缩小图片，支持本地和网络图片资源。若是网络图片资源则会被缓存到本地，缓存到本地上的资源可以通过 clearCache 接口手动清除。同时本模块支持横竖屏显示，在本app支持横竖屏的情况下，本模块底层会自动监听当前设备的位置状态，自动适配横竖屏以展示图片。使用此模块开发者看实现炫酷的图片浏览器。

### 文档
[http://docs.apicloud.com/Client-API/Func-Ext/photoBrowser](http://docs.apicloud.com/Client-API/Func-Ext/photoBrowser)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/photoBrowser](#https://github.com/apicloudcom/photoBrowser)


## ble

蓝牙4.0模块

### 文档
[http://docs.apicloud.com/Client-API/Device-Access/ble](http://docs.apicloud.com/Client-API/Device-Access/ble)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/ble](#https://github.com/apicloudcom/ble)


## pedometer

手机计步器模块

### 文档
[http://docs.apicloud.com/Client-API/Device-Access/pedometer](http://docs.apicloud.com/Client-API/Device-Access/pedometer)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/pedometer](#https://github.com/apicloudcom/pedometer)


## aMap

高德地图模块

### 文档
[http://docs.apicloud.com/Client-API/Open-SDK/aMap](http://docs.apicloud.com/Client-API/Open-SDK/aMap)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/moduleCode/aMap](#https://github.com/apicloudcom/moduleCode/aMap)


## bMap

百度地图模块

### 文档
[http://docs.apicloud.com/Client-API/Open-SDK/bMap](http://docs.apicloud.com/Client-API/Open-SDK/bMap)  

### 信息
- 可用性：iOS系统，Android系统
- 费用：免费
- 来源：APICloud 官方
- 开源地址：[https://github.com/apicloudcom/bMap](#https://github.com/apicloudcom/bMap)
