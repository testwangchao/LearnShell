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
```find -iname``` 忽略大小写

2. 否定参数

匹配所有不以.txt结尾的文件名
```
find . ! -name "*.txt" -print
```

3. 基于目录深度的搜索

将find命令向下的最大深度限制为1
```
find . -maxdepth 1 -name "f*" -print
```

-mindepth类似于 -maxdepth，不过它设置的是find开始遍历的最小深度。

4. 根据文件类型搜索

搜索目录
```
find . -type d
```
|文件类型 |类型参数|
| -----  |-------|
|普通文件 |f|
|符号链接 |l|
|目录 |d|
|字符设备 |c|
|块设备 |b|
|套接字 |s|
|FIFO |p|

5.删除匹配的文件

-delete可以用来删除find查找到的匹配文件。

删除当前目录下所有的 .swp文件：
```
$ find . -type f -name "*.swp" -delete
```

#### find和xargs

xargs和find算是一对死党。两者结合使用可以让任务变得更轻松。不过人们通常却是以一
种错误的组合方式使用它们。例如：
```$ find . -type f -name "*.txt" -print | xargs rm -f```
这样做很危险。有时可能会删除不必要删除的文件。我们没法预测分隔find命令输出结果
的定界符究竟是什么（'\n'或者' '）。很多文件名中都可能会包含空格符（' '），因此xargs
很可能会误认为它们是定界符（例如，hell text.txt会被xargs误解为hell和text.txt）。
只要我们把find的输出作为xargs的输入，就必须将 -print0与find结合使用，以字符null
（'\0'）来分隔输出。

- 删除文件
  ```
    $ find . -type f -name "*.txt" -print0 | xargs rm -f
  ```

- 统计源代码目录中所有python文件的行数
  ```
  find . -type f -name '*.py' -print0 | xargs -0 wc -l
  ```

  5 ./test_porn.py