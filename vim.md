![logo](http://oop4q34sz.bkt.clouddn.com/vim_logo.png)

# Vim

![logo](http://oop4q34sz.bkt.clouddn.com/vim-11.png)

> Vim（Vi[Improved]）编辑器是功能强大的跨平台文本文件编辑工具，继承自Unix系统的Vi编辑器，支持Linux/Mac OS X/Windows系统，利用它可以建立、修改文本文件。

<!-- [pwd](#pwd) [cd](#cd) [ls](#ls) [mkdir](#mkdir) [touch](#touch) [wc](#wc) [cat](#cat) [rm](#rm) [mv](#mv) [cp](#cp) -->

## 进入 vim
进入Vim编辑窗口，可以在终端输入下面的命令

### 语法
vim [filename]

- filename: 文件路径

### 实例

```Bash
$ vim ~/vim_test.txt
```

## 正常模式

|  命令  |  说明  |
|  ---  |  ---  |
|  x  |  删除一个字符  |
|  u  |  辙销操作，可多次使用  |
|  e  |  跳到词尾  |
|  p  |  粘贴  |
|  r  |  替换一个字母，按 r 松开，然后再按新字母  |
|  i  |  进入编辑模式，当前光标处插入  |
|  a  |  进入编辑模式，当前光标后插入  |
|  A  |  进入编辑模式，光标移动到行尾  |
|  o  |  进入编辑模式，当前行下面插入新行  |
|  O  |  进入编辑模式，当前行上面插入新行  |
|  k  |  移动光标，向上  |
|  j  |  移动光标，向下  |
|  h  |  移动光标，向左  |
|  l  |  移动光标，向右  |
|  dd  |  删除当前行  |
|  dw  |  删除一个单词  |
|  yy  |  复制当前行  |
|  ZZ  |  保存并退出  |
|  ctrl+f  |  向前翻页  |
|  ctrl+b  |  向后翻页  |

## 命令模式

|  命令  |  说明  |
|  ---  |  ---  |
|  :w  |  保存  |
|  :w filenme  |  另存为  |
|  :q  |  退出  |
|  :wq  |  保存并退出  |
|  :e!  |  撤销更改，返回到上一次保存的状态  |
|  :q!  |  不保存强制退出  |
|  :set nu  |  设置行号  |
