# note
记录平时碰到的一些知识点<br>

## oracle
### 函数
* **instr函数：从一个字符串中查找指定子串的位置**<br>
如：select instr('张12138','38') from dual; 结果是：5。'38'开始出现在第五位<br>
注意:其返回结果从1开始，0代表没有<br>
应用：判断字符是否以XX开头，where instr(t.name,'佰盈')=1

## Java
### [JavaWeb工程师之路](http://ke.jikexueyuan.com/zhiye/javaweb/)
  按照这条路，开始学习吧
### eclipse
#### 快捷键
**[资料](http://www.cnblogs.com/mq0036/p/4995390.html)**
* **alt+/：自动补全代码或者提示代码**
* **Ctrl+1：快速修正**
* **ctrl+shift+r：打开资源列表**：搜索项目中的java,jsp等文件
* **ctrl+O（字母O）：快速outline视图** 
* **ctrl+e：快速转换编辑器**：当你打开很多文件时使用比较快捷
* **ctrl+shift+o：自动引入包和删除无用包**
* **ctrl+page down或ctrl+page up： 选项卡之间快速切换**：可以浏览前后的选项卡，如果使用熟练的话，各个页面切换会非常的快，感觉很不错。
* **ctrl+m：当前编辑页面窗口最大化**：再按一下恢复
* **ctrl+shift+x和ctrl+shift+y：英文字母大小写的转换**
* **Ctrl+L:快速跳到某行**：查看日志时提示某行错误可以使用这个快速定位
* **F4：打开选中元素的类型继承结构**
* **Ctrl+Shift+G：在workspace中搜索选中元素的引用**

### 正则表达式[资料](http://www.cnblogs.com/lzq198754/p/5780340.html)
split(regex),match
如："|"在正则表达式中代表或，所以要转义  "\\\\|"

### java TCP/IP SOCKET编程
极客学院-[java TCP/IP SOCKET编程](http://wiki.jikexueyuan.com/project/java-socket/overwise.html)<br>
慕课网-[java socket](http://www.imooc.com/learn/161)

## android
## [Android工程师](http://ke.jikexueyuan.com/zhiye/android/)
java为主，同时学些Android充实一下，不然只学Java太无聊了
### androidstudio
#### 快捷键
**[资料1](http://www.cnblogs.com/zyw-205520/p/5231843.html)**
* **ctrl+N**:查找类----eclipse:ctrl+shift+R
* **ctrl+shift+N**:快速查找文件
* **Alt＋Insert可以生成构造器/Getter/Setter等**
* **Ctrl＋Shift＋Space在很多时候都能够给出Smart提示**  没eclipse有用
* **Ctrl＋O（字母O）可以选择父类的方法进行重写**
* **Ctrl＋Alt＋Space是类名自动完成**--eclipse的ALT+/（智能提示）的功能相当于把这个和ctrl+shift+space合起来了
* **Alt＋F8是计算变量值**
* **Alt+回车 导入包,自动修正**
* **Ctrl+H 显示类结构图**
* **Shift+F6  重构-重命名**：第一次按选中，第二次按重构，使用时要按两次
* **Ctrl+E 最近打开的文件**

### 动画-animation
#### 极客学院-[Animation动画详解](http://wiki.jikexueyuan.com/project/android-animation)
* **alpha、scale、translate、rotate、set 的 xml 属性及用法**  
* **Interpolator 插值器**
* **代码生成 alpha、scale、translate、rotate、set 及插值器动画**

## ps


