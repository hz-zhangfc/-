<h1>你大爷的oracle错题集</h1>
<h2>sql执行的优先级</h2>
<strong>这tm是最tm重要的东西之一，很多问题看看这个就能够解决</strong>
<pre>
  (8)SELECT (9)DISTINCT  (11)&lt;Top Num> &lt;select list>
  (1)FROM [left_table]
  (3)&lt;join_type> JOIN &lt;right_table>
  (2)ON &lt;join_condition>
  (4)WHERE &lt;where_condition>
  (5)GROUP BY &lt;group_by_list>
  (6)WITH &lt;CUBE | RollUP>
  (7)HAVING &lt;having_condition>
  (10)ORDER BY &lt;order_by_list>
</pre>
<ol>
   <li>FROM：对FROM子句中的前两个表执行笛卡尔积（Cartesian product)(交叉联接），生成虚拟表VT1</li>
   <li>ON：对VT1应用ON筛选器。只有那些使<join_condition>为真的行才被插入VT2。
   <li>OUTER(JOIN)：如 果指定了OUTER JOIN（相对于CROSS JOIN 或(INNER JOIN),保留表
   （preserved table：左外部联接把左表标记为保留表，右外部联接把右表标记为保留表，完全外部联接把两个表都标记为保留表）
   中未找到匹配的行将作为外部行添加到 VT2,生成VT3.如果FROM子句包含两个以上的表，
   则对上一个联接生成的结果表和下一个表重复执行步骤1到步骤3，直到处理完所有的表为止。</li>
   <li>WHERE：对VT3应用WHERE筛选器。只有使<where_condition>为true的行才被插入VT4.</li>
   <li>GROUP BY：按GROUP BY子句中的列列表对VT4中的行分组，生成VT5.</li>
   <li>CUBE|ROLLUP：把超组(Suppergroups)插入VT5,生成VT6.</li>
   <li>HAVING：对VT6应用HAVING筛选器。只有使<having_condition>为true的组才会被插入VT7.</li>
   <li>SELECT：处理SELECT列表，产生VT8.</li>
   <li>DISTINCT：将重复的行从VT8中移除，产生VT9.</li>
   <li>ORDER BY：将VT9中的行按ORDER BY 子句中的列列表排序，生成游标（VC10).</li>
   <li>TOP：从VC10的开始处选择指定数量或比例的行，生成表VT11,并返回调用者。</li>
</ol>
<h2>该死的左右连接(left/right/full out join)</h2>
<strong>先介绍一下两种使用方法</strong>
<pre>
  select * from t1 left join t2 on t1.urid = t2.urid;
  select * from t1,t2 where t1.urid=t2.urid(+);
  <strong>这两句话是一样的</strong>
</pre>
<h3>left join的on和where的冲突</h3>
<pre>
  前提条件：t1,2是有数据的，t1,2通过urid关联。还有一个查询条件会导致t2查为空
  select t1.urid from t1,t2 where t1.urid = t2.urid(+) and t2.name='一个错误条件，会导致t2查不出数据来';
  因为是t1左连接t2，按照道理应该会有数据，然而现实是查不出数据来
</pre>
<strong>分析</strong>
<pre>
  将刚才sql翻译
  select t1.urid from t1 left join t2 on t1.urid = t2.urid where t2.name='一个错误条件，会导致t2查不出数据来';
  <b>看看上面sql执行的优先级,t1 left join t2后产生的中间表的数据又被where的条件搞没了</b>
  <strong>修改后</strong>
  select t1.urid from t1 left join t2 on t1.urid = t2.urid and t2.name='一个错误条件，会导致t2查不出数据来';
  或者
  select t1.urid from t1,t2 where t1.urid = t2.urid(+) where t2.name(+)='一个错误条件，会导致t2查不出数据来';
</pre>
