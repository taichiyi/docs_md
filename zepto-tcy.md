
# zepto-tcy


[$()](#$()) [append](#append) [before](#before) [prepend](#prepend) [after](#after) [slice](#slice) [get](#get) [size](#size) [remove](#remove) [each](#each) [eq](#eq) [find](#find) [parent](#parent) [children](#children) [prev](#prev) [next](#next) [show](#show) [hide](#hide) [html](#html) [attr](#attr) [removeAttr](#removeAttr) [prop](#prop) [removeProp](#removeProp) [data](#data) [val](#val) [width](#width) [height](#height) [css](#css) [hasClass](#hasClass) [addClass](#addClass) [removeClass](#removeClass) [scrollTop](#scrollTop) [click](#click)


## 简介

**Zepto-tcy**是一个轻量级的**针对现代手机浏览器的JavaScript库**，它与jquery**有着类似的api**。 如果你会用jquery，那么你也会用zepto-tcy。

基于zepto.js精简改良, 性能更好, 更轻量. 主要针对的是webkit内核的手机浏览器, 所以无需考虑太多.

## API

### $()

$(selector)   ⇒ collection

选择器只支持三种: class, id, 元素

```javascript
$('body'), $('li') // 元素
$('.li'), $('.list') // class
$('#ul') // id
```

### append

append(content)   ⇒ self

在首个匹配的元素的结束标签之前插入内容。内容只能为html字符串。

```javascript
$('body').append('<li>new list item</li>')
```

### before

before(content)   ⇒ self

在首个匹配的元素的开始标签之前插入内容。内容只能为html字符串。

```javascript
$('body').before('<li>new list item</li>')
```

### prepend

prepend(content)   ⇒ self

在首个匹配的元素的开始标签之后插入内容。内容只能为html字符串。

```javascript
$('body').prepend('<li>new list item</li>')
```

### after

after(content)   ⇒ self

在首个匹配的元素的结束标签之后插入内容。内容只能为html字符串。

```javascript
$('body').after('<li>new list item</li>')
```

### slice

slice(start, [end])   ⇒ array

提取这个数组`array`的子集，从`start`开始，如果给定`end`，提取从从`start`开始到`end`结束的元素，但是不包含`end`位置的元素。

```javascript
$('.li').slice(1,2)
```

### get

get()   ⇒ array

get(index)   ⇒ DOM node

从当前对象集合中获取所有元素或单个元素。当index参数不存在的时，以普通数组的方式返回所有的元素。当指定index时，只返回该置的元素。这点与eq不同，该方法返回的是DOM节点，不是Zepto对象集合。

```javascript
$('.li').get()
$('.li').get(0)
```

### size

size()   ⇒ number

获取对象集合中元素的数量。

```javascript
$('.li').size()
```

### remove

remove()   ⇒ self

删除元素包含子元素。

```javascript
$('.li').remove()
```

### each

each()   ⇒ self

遍历一个对象集合每个元素。在迭代函数中，`this`关键字指向当前项(作为函数的第二个参数传递)。如果迭代函数返回 `false`，遍历结束。

```javascript
$('.li').each(function(idx, el) {
    console.log(idx);
    console.log(el);
});
```

### eq

eq(index)   ⇒ collection

从当前对象集合中获取给定索引值（以0为基数）的元素。

```javascript
$('.li').eq(0) // 选取第一个
$('.li').eq(1) // 选取第二个
$('.li').eq(-1) // 选取最后一个
```

### find

find(selector)   ⇒ collection

在当前对象集合内查找符合CSS选择器的每个元素的后代元素。selector只支持两种选择器: class和id

```javascript
$('.li').find('.li1') // class选择器
$('.li').find('#li4') // id选择器
$('#div1').find('.div1-p') // class选择器
```

### parent

parents()   ⇒ collection

返回对象集合的第一个元素的父元素

```javascript
$('#div').parent()
```

### children

children()   ⇒ collection

返回对象集合的第一个元素的子元素

```javascript
$('#div').children()
```

### prev

prev()   ⇒ collection

返回对象集合中第一个元素的前一个兄弟节点

```javascript
$('#div').prev()
```

### next

next()   ⇒ collection

返回对象集合中第一个元素的后一个兄弟节点

```javascript
$('#div').next()
```

### show

show()   ⇒ self

对象集合中每个元素的“display”值设置为`block`。

```javascript
$('#div').show()
$('.li').show()
```

### hide

hide()   ⇒ self

对象集合中每个元素的“display”值设置为`none`。

```javascript
$('#div').hide()
$('.li').hide()
```

### html

html()   ⇒ string

html(content)   ⇒ self

获取或设置对象集合中元素的HTML内容。

```javascript
$('body').html() // 取值
$('body').html('zepto-tcy') // 设值
```

### attr

attr(name)   ⇒ string

attr(content)   ⇒ self

获取或设置对象集合中元素的HTML内容。

```javascript
$('body').attr('class') // 取值
$('body').attr('class', '.body') // 设值
```

### removeAttr

removeAttr(name)   ⇒ self

移除当前对象集合中所有元素的指定属性。

```javascript
$('body').removeAttr('class')
```

### prop

prop(name)   ⇒ self

读取或设置dom元素的属性值。它在读取属性值的情况下优先于 [attr](http://www.css88.com/doc/zeptojs_api/#attr)，因为这些属性值会因为用户的交互发生改变，如`checked` 和 `selected`。

简写或小写名称，比如`for`, `class`, `readonly`及类似的属性，将被映射到实际的属性上，比如`htmlFor`, `className`, `readOnly`, 等等。

```javascript
$('.checkbox').prop('checked')
```

### removeProp

removeProp(name)   ⇒ self

从集合的每个DOM节点中删除一个属性。这是用JavaScript的`delete`操作符完成。值得注意的是如果尝试删除DOM的一些内置属性，如`className`或`maxLength`，将不会有任何效果，因为浏览器禁止删除这些属性。

```javascript
$('.checkbox').removeProp('checked')
```

### data

data(name)   ⇒ value
data(name, value)   ⇒ self

读取或写入dom的 `data-*` 属性。行为有点像 `attr`，但是属性名称前面加上 `data-`。

```javascript
$('body').data('url')
$('body').data('url', 'http://www.qq.com/')
```

### val

val()   ⇒ string
val(value)   ⇒ self

获取或设置匹配元素的值。

```javascript
$('#input1').val()
$('#input1').val('123456')
```

### width

width()   ⇒ number
width(value)   ⇒ self

获取或设置匹配元素的值。

```javascript
$('body').width()
$('body').width('100px')
```

### height

height()   ⇒ number
height(value)   ⇒ self

获取或设置匹配元素的值。

```javascript
$('body').height()
$('body').height('100px')
```

### css

css(property)   ⇒ value

css(property, value)   ⇒ self

获取或设置匹配元素的值。

```javascript
$('body').css('height')
$('body').css('display', 'none')
```

### hasClass

hasClass(name)   ⇒ boolean

检查对象集合中是否有元素含有指定的class。

```javascript
$('body').hasClass('body')
```

### addClass

addClass(name)   ⇒ self

为每个匹配的元素添加指定的class类名。

```javascript
$('body').addClass('body')
```

### removeClass

removeClass([name])   ⇒ self

移除当前对象集合中所有元素的指定class。多个class参数名称可以利用空格分隔。

```javascript
$('body').removeClass('body')
$('#div').removeClass('active div2')
```

### scrollTop

scrollTop(value)   ⇒ self

获取或设置页面上的滚动元素或者整个窗口向下滚动的像素值。

```javascript
$('body').scrollTop()
$('body').scrollTop(100)
```

### click

click()   ⇒ self

触发对象集合的第一个元素的点击事件

```javascript
$('body').click()
```

### 



