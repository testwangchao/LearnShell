#### grep
    grep的工作方式：它在一个或多个文件中搜索字符串模板。如果模板包括空格，则必须被引用，模板后的所有字符串被看作文件名。搜索的结果被送到标准输出，不影响原文件内容。


1. grep -c:显示匹配的数目
```
root at wangchao-virtual-machine in /home/wangchao/Learn/grep
$ cat grep-c.txt
Today is a good day,because the girl I like tell me she like me too.
So,I am very happy.
But I have to learn the grep command,so I only Learn.
This is a test text!
This is a test2 text!
This is a test3 text!
test7,test8.
This is a test4 text!
This is a test5 text!

root at wangchao-virtual-machine in /home/wangchao/Learn/grep
$ grep -c 'test' grep-c.txt
6
```
2. 从文件中读取关键词进行搜索
```

root at wangchao-virtual-machine in /home/wangchao/Learn/grep
$ cat test.txt
test
test2

root at wangchao-virtual-machine in /home/wangchao/Learn/grep
$ cat grep-c.txt| grep -f test.txt
This is a test text!
This is a test2 text!
This is a test3 text!
test7,test8.
This is a test4 text!
This is a test5 text!
```
3. 从文件中读取关键词进行搜索 且显示行号
```
root at wangchao-virtual-machine in /home/wangchao/Learn/grep
$ cat grep-c.txt| grep -nf test.txt
4:This is a test text!
5:This is a test2 text!
6:This is a test3 text!
7:test7,test8.
8:This is a test4 text!
9:This is a test5 text!
```
4. grep -v 筛选不匹配的行

#### find 目录 参数
1. -name按文件名查找文件<br>
查找grep目录下所有的txt文件
```
root at wangchao-virtual-machine in /home/wangchao/Learn
$ find grep -name '*.txt'
grep/grep-c.txt
grep/test.txt
```
2. -perm 按照文件权限查找