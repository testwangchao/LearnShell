#### 一.在命令行使用sed命令
1. 修改数据:将Test替换为test输出到STDOUT不改变文件的原始数据,默认情况下只能替换每行中出现的第一处
[root@bogon LearnSed]# sed s/Test/test/ test1
This is a test1!
This is a test2!
This is a test3!
This is a test4!
This is a test5!
This is a test6!
This is a test7!

[root@bogon LearnSed]# cat test1
This is a Test1!
This is a Test2!
This is a Test3!
This is a Test4!
This is a Test5!
This is a Test6!
This is a Test7!
2. 在命令行使用多个编辑器命令
命令之间以分号分割，并且在命令末尾和分号之间不能有空格
[root@bogon LearnSed]# sed -e 's/This/this/; s/Test/test/' test1
this is a test1!
this is a test2!
this is a test3!
this is a test4!
this is a test5!
this is a test6!
this is a test7!
3. 从文件中读取编辑器命令
如果有大量要处理的sed命令，可以将它们放入文件，使用sed -f 命令文件 处理文本
[root@bogon LearnSed]# vim script
  1 s/Test/test/
  2 s/This/this/
[root@bogon LearnSed]# sed -f script test1 
this is a test1!
this is a test2!
this is a test3!
this is a test4!
this is a test5!
this is a test6!
this is a test7!
4. 替换标记（多出替换）
数字：表明新文本将替换第几处模式匹配的地方
将第三处匹配的文本替换
[root@bogon LearnSed]# sed s/Test/test/3 test1 
This is a Test1 Test1 test1!
This is a Test2 Test2!  
This is a Test3!
This is a Test4!
This is a Test5!
This is a Test6!
This is a Test7!
g:表明新文本将替换所有的替换文本
[root@bogon LearnSed]# sed s/Test/test/g test1 
This is a test1 test1 test1!
This is a test2 test2!  
This is a test3!
This is a test4!
This is a test5!
This is a test6!
This is a test7!
``
