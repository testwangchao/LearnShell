#### 一.在命令行使用sed命令
1. 修改数据:将Test替换为test输出到STDOUT不改变文件的原始数据,默认情况下只能替换每行中出现的第一处
[root@bogon LearnSed]# sed s/Test/test/ test1<br>
This is a test1!<br>
This is a test2!<br>
This is a test3!<br>
This is a test4!<br>
This is a test5!<br>
This is a test6!<br>
This is a test7!<br>

[root@bogon LearnSed]# cat test1<br>
This is a Test1!<br>
This is a Test2!<br>
This is a Test3!<br>
This is a Test4!<br>
This is a Test5!<br>
This is a Test6!<br>
This is a Test7!<br>

2. 在命令行使用多个编辑器命令
命令之间以分号分割，并且在命令末尾和分号之间不能有空格<br>
[root@bogon LearnSed]# sed -e 's/This/this/; s/Test/test/' test1<br>
this is a test1!<br>
this is a test2!<br>
this is a test3!<br>
this is a test4!<br>
this is a test5!<br>
this is a test6!<br>
this is a test7!<br>

3. 从文件中读取编辑器命令
如果有大量要处理的sed命令，可以将它们放入文件，使用sed -f 命令文件 处理文本<br>
[root@bogon LearnSed]# vim script<br>
  1 s/Test/test/<br>
  2 s/This/this/<br>
[root@bogon LearnSed]# sed -f script test1 <br>
this is a test1!<br>
this is a test2!<br>
this is a test3!<br>
this is a test4!<br>
this is a test5!<br>
this is a test6!<br>
this is a test7!<br>

4. 替换标记（多出替换）
数字：表明新文本将替换第几处模式匹配的地方<br>
将第三处匹配的文本替换<br>
[root@bogon LearnSed]# sed s/Test/test/3 test1 <br>
This is a Test1 Test1 test1!<br>
This is a Test2 Test2!  <br>
This is a Test3!<br>
This is a Test4!<br>
This is a Test5!<br>
This is a Test6!<br>
This is a Test7!<br>
g:表明新文本将替换所有的替换文本<br>
[root@bogon LearnSed]# sed s/Test/test/g test1 <br>
This is a test1 test1 test1!<br>
This is a test2 test2!  <br>
This is a test3!<br>
This is a test4!<br>
This is a test5!<br>
This is a test6!<br>
This is a test7!<br>

5. 插入数据
insert：命令i会在指定行前添加一个新行<br>
[root@localhost test]# cat state <br>
China<br>
New York<br>
Japan<br>
zhong guo<br>
China is best!<br>
China is good!<br>

[root@localhost test]# sed '2i\This is test' state <br>
China<br>
This is test<br>
New York<br>
Japan<br>
zhong guo<br>
China is best!<br>
China is good!<br>

[root@localhost test]# sed '2,4i\This is test' state <br>
China<br>
This is test<br>
New York<br>
This is test<br>
Japan<br>
This is test<br>
zhong guo<br>
China is best!<br>
China is good!<br>

append：命令a会在指定行后增加一个新行<br>
[root@localhost test]# cat state <br>
China<br>
New York<br>
Japan<br>
zhong guo<br>
China is best!<br>
China is good!<br>
[root@localhost test]# sed '2a\This is test!' state <br>
China<br>
New York<br>
This is test!<br>
Japan<br>
zhong guo<br>
China is best!<br>
China is good!<br>

追加多行文本<br>
[root@localhost test]# sed '1i\
> test1\
> test2 ' state

test1
test2 
China
New York
Japan
zhong guo
China is best!
China is good!

6. 修改文本
替换第一行<br>
[root@localhost test]# sed '1c test' state <br>
test<br>
New York<br>
Japan<br>
zhong guo<br>
China is best!<br>
China is good!<br>

7. sed -n:只有经过sed 特殊处理的那一行(或者动作)才会被列出来。
root@localhost test]# se# -n '/China/p' state <br>
China<br>
China is best!<br>
China is goo#!<br>
China test<br>

8. 打印行号
[root@localhost test]# sed -n '/China/{<br>
> =<br>
> p<br>
> }' state<br>
1<br>
China<br>
5<br>
China is best!<br>
6<br>
China is good!<br>
8<br>
China test<br>
