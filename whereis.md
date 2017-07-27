#### whereis在数据库中查找数据
1. whereis -b:定位二进制文件（可执行文件）
```
root at wangchao-virtual-machine in /usr/bin
$ whereis -b python
python: /usr/bin/python /usr/bin/python3.5 /usr/bin/python3.5m /usr/bin/python2.7 /usr/lib/python3.5 /usr/lib/python2.7 /usr/lib/python3.6 /etc/python /etc/python3.5 /etc/python2.7 /usr/local/lib/python3.5 /usr/local/lib/python2.7 /usr/include/python3.5m /usr/share/python
```
2. whereis -B：定位二进制文件所在的路径
3. whereis -s:定位源文件
4. whereis -S:定位源文件所在的路径
5. whereis 文件名称:将于文件相关的内容都查询出来

#### which 查找可执行文件的位置

####