# -note
记录平时碰到的一些知识点<br>

oracle
--
instr函数：从一个字符串中查找指定子串的位置<br>
  如：select instr('张12138','3') from dual; 结果是：5。'3'出现在第五位<br>
  应用：判断字符是否以XX开头，instr(t.name,'佰盈')=0
