# -note
记录平时碰到的一些知识点<br>

## oracle
### 函数
#### instr函数：从一个字符串中查找指定子串的位置<br>
如：select instr('张12138','38') from dual; 结果是：5。'38'开始出现在第五位<br>
注意:其返回结果从1开始，0代表没有<br>
应用：判断字符是否以XX开头，where instr(t.name,'佰盈')=1

## Java
### 正则表达式[资料](http://www.cnblogs.com/lzq198754/p/5780340.html)
split(regex),match
如："|"在正则表达式中代表或，所以要转义  "\\\\|"
