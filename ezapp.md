
# ezapp.js


[openWin](#openwin) [openFrame](#openframe) [cache](#cache) [type](#type) [isPC](#ispc) [isIOS](#isios) [extend](#extend) [statusBarHeight](#statusbarheight) [ready](#ready) [loadFile](#loadfile)


## 简介

**ezapp**是APICloud的一个库

## openWin

打开window

通过此方法打开window, 会创建一个名为`name`+Params的localStorage, 如果此方法在window里调用, 则localStorage默认值为: {from: `此window的name`}; 如果此方法在frame里调用, 则localStorage默认值为: {from: `此frame的name`}

openWin({params})

具体内容参照官方文档[http://docs.apicloud.com/Client-API/api#33](http://docs.apicloud.com/Client-API/api#33) 

#### 默认值

url

- 类型：字符串
- 默认值：`name ` + '.html'

bounces

- 类型：布尔
- 默认值：false

slidBackEnabled

- 类型：布尔
- 默认值：false

vScrollBarEnabled

- 类型：布尔
- 默认值：false

hScrollBarEnabled

- 类型：布尔
- 默认值：false

softInputMode

- 类型：字符串
- 默认值：'pan'
- 描述：只iOS有效

bgColor

- 类型：字符串
- 默认值：#f7f8f9

animation

- 类型：JSON 对象

- 默认值：

  ```
  {
      type: 'movein', //动画类型（详见动画类型常量）
      subType: 'from_right', //动画子类型（详见动画子类型常量）
      duration: 300 //动画过渡时间
  }
  ```

pageParam

- 类型：JSON 对象

- 默认值：无
- 描述：pageParam会追加到localStorage里

#### 实例

打开登录页面, 只传一个`name`, 且`name`为login

```javascript
// 下面的代码在name为 home 的window下运行
Q.openWin('login');
// 实际上为↓
api.openWin({
  name: 'login',
  url: 'login.html',

  bounces: false,
  slidBackEnabled: false,
  vScrollBarEnabled: false,
  hScrollBarEnabled: false,
  softInputMode: 'pan',
  bgColor: '#f7f8f9',
  animation:{
    type: 'movein',
    subType: 'from_right',
    duration: 300
  }
});
// 并创建了一个名为loginParams, 值为{from: 'home'}的localStorage. 可以同过Q.cache.get('loginParams')来获取
```

打开注册(reg)页面, 并设置localStorage

```javascript
// 下面的代码在name为 home_frame 的frame下运行
Q.openWin({
  name: 'reg',
  bgColor: 'rgba(0, 0, 0, 0.0)',
  allowEdit: true,
  pageParam: {
    title: '注册',
    info: {time: 123, user: 'amdin'}
  }
});
// 实际上为↓
api.openWin({
  name: 'login',
  url: 'login.html',
  bgColor: 'rgba(0, 0, 0, 0.0)',
  allowEdit: true,
  pageParam: {
    title: '注册',
    info: {time: 123, user: 'amdin'}
  },

  bounces: false,
  slidBackEnabled: false,
  vScrollBarEnabled: false,
  hScrollBarEnabled: false,
  softInputMode: 'pan',
  animation:{
    type: 'movein',
    subType: 'from_right',
    duration: 300
  }
});
// 并创建了一个名为regParams, 值为{from: 'home_frame', title: '注册', info: {time: 123, user: 'amdin'}}的localStorage. 可以同过Q.cache.get('regParams')来获取
```

## openFrame

打开frame

通过此方法打开frame, 会创建一个名为`name`+Params的localStorage, 如果此方法在window里调用, 则localStorage默认值为: {from: `此window的name`}; 如果此方法在frame里调用, 则localStorage默认值为: {from: `此frame的name`}

openFrame({params})

具体内容参照官方文档[http://docs.apicloud.com/Client-API/api#33](http://docs.apicloud.com/Client-API/api#33) 

#### 默认值

url

- 类型：字符串
- 默认值：`name ` + '.html'

bounces

- 类型：布尔
- 默认值：false

slidBackEnabled

- 类型：布尔
- 默认值：false

vScrollBarEnabled

- 类型：布尔
- 默认值：false

hScrollBarEnabled

- 类型：布尔
- 默认值：false

softInputMode

- 类型：字符串
- 默认值：'auto'
- 描述：只iOS有效

bgColor

- 类型：字符串
- 默认值：rgba(0, 0, 0, 0.0)

animation

- 类型：JSON 对象

- 默认值：

  ```
  {
      type:"none",                //动画类型（详见动画类型常量）
      subType:"from_right",       //动画子类型（详见动画子类型常量）
      duration:300                //动画过渡时间，默认300毫秒
  }
  ```

pageParam

- 类型：JSON 对象


- 默认值：无
- 描述：pageParam会追加到localStorage里

#### 实例

打开筛选页面, 只传一个`name`, 且`name`为filter

```javascript
// 下面的代码在name为 home 的window下运行
Q.openFrame('filter');
// 实际上为↓
api.openFrame({
  name: 'filter',
  url: 'filter.html',

  bounces: false,
  slidBackEnabled: false,
  vScrollBarEnabled: false,
  hScrollBarEnabled: false,
  softInputMode: 'auto',
  bgColor: 'rgba(0,0,0,0.0)',
});
// 并创建了一个名为filterParams, 值为{from: 'home'}的localStorage. 可以同过Q.cache.get('filterParams')来获取
```

打开筛选(filter)页面, 并设置localStorage

```javascript
// 下面的代码在name为 home_frame 的frame下运行
Q.openFrame({
  name: 'filter',
  bgColor: 'rgba(0, 0, 0, 0.0)',
  allowEdit: true,
  pageParam: {
    title: '注册',
    info: {time: 123, user: 'amdin'}
  }
});
// 实际上为↓
api.openFrame({
  name: 'filter',
  url: 'filter.html',
  bgColor: 'rgba(0, 0, 0, 0.0)',
  allowEdit: true,
  pageParam: {
    title: '注册',
    info: {time: 123, user: 'amdin'}
  },

  bounces: false,
  slidBackEnabled: false,
  vScrollBarEnabled: false,
  hScrollBarEnabled: false,
  softInputMode: 'auto'
});
// 并创建了一个名为filterParams, 值为{from: 'home_frame', title: '注册', info: {time: 123, user: 'amdin'}}的localStorage. 可以同过Q.cache.get('filterParams')来获取
```

## cache

设置或获取localStorage.

#### cache.set

设置localStorage.

Q.cache.set(key, value)

key:

- 类型：字符串
- 默认值：无
- 描述：localStorage名称

value:

- 类型：字符串
- 默认值：无
- 描述：localStorage值

#### 实例

```javascript
Q.cache.set('loginParams', {from: 'root', type: 1});
Q.cache.set('username', 'admin');
Q.cache.set('user_id', 6);
```



#### cache.get

获取localStorage.

Q.cache.get(key)

key:

- 类型：字符串
- 默认值：无
- 描述：localStorage名称

#### 实例

```javascript
Q.cache.get('loginParams');
Q.cache.get('username');
Q.cache.get('user_id');
```

## type

返回变量类型

Q.type(value)   ⇒ return

value:

- 类型：任何类型
- 默认值：无
- 描述：待判断类型的变量

return:

- 类型：任何类型
- 默认值：'undefined'
- 返回值：

```
数值：number
字符串：string
布尔值：boolean
undefined：undefined
null：null
数组：array
arguments对象：arguments
函数：function
Error对象：error
Date对象：date
RegExp对象：regexp
其他对象：object
```



#### 实例

```javascript
Q.type(''); // string
Q.type('account'); // string
Q.type(123); // number
Q.type(299.99); // number
Q.type(false); // boolean
Q.type(true); // boolean
Q.type(undefined); // undefined
Q.type(null); // null
Q.type([]); // array
Q.type({}); // object
Q.type(arguments); // arguments
Q.type(function(){}); // function
Q.type(new Date); // date
Q.type(/^123$/); // regexp
```

## isPC

是否为pc

Q.isPC()   ⇒ return

return:

- 类型：布尔
- 默认值：无
- 描述：如果当前环境是PC返回true, 否则返回false

## isIOS

是否为ios

Q.isIOS()   ⇒ return

return:

- 类型：布尔
- 默认值：无
- 描述：如果当前环境是ios返回true, 否则返回false

## extend

对象合并

如果def_params对象和params对象有相同的属性, 则params对象的属性覆盖def_params对象的属性。支持多维对象

Q.extend({def_params}, {params})

def_params:

- 类型：JSON对象
- 默认值：无
- 描述：def_params

params:

- 类型：JSON对象
- 默认值：无
- 描述：params

## statusBarHeight

获取沉浸式高度

Q.statusBarHeight()   ⇒ return

return:

- 类型：数字
- 默认值：无
- 描述：如果不支持沉浸式返回0; 反之ios返回20, android返回25

## ready

当api对象加载到window全局对象时,调用此函数

Q.ready(function(){})

#### 实例

```javascript
Q.ready(function() {
    // api对象已加载
});
```

## loadFile

异步加载文件, 如.js, .json, .css

Q.loadFile({params}, callback(ret))

#### params

url:

- 类型：字符串
- 默认值：无
- 描述：文件地址

#### callback

ret:

- 类型：JSON对象
- 描述：成功
- 内部字段：

```
{
  data: ''  // 文件内容
}
```

#### 实例

```javascript
Q.loadFile({
    url: '../res/city-data.json'
}, function(ret, err) {
    console.log(JSON.stringify(ret));
});
```

