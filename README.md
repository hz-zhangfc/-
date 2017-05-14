# note
记录平时碰到的一些知识点<br>

## oracle
### 函数
* **instr函数：从一个字符串中查找指定子串的位置**<br>
如：select instr('张12138','38') from dual; 结果是：5。'38'开始出现在第五位<br>
注意:其返回结果从1开始，0代表没有<br>
应用：判断字符是否以XX开头，where instr(t.name,'佰盈')=1

## Java
### 正则表达式[资料](http://www.cnblogs.com/lzq198754/p/5780340.html)
split(regex),match
如："|"在正则表达式中代表或，所以要转义  "\\\\|"

## android
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


