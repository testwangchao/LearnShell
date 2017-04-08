#### 文件系统的相关命令
##### ls
1. ls -F 区分文件和目录
2. ls -a 显示所有的文件（包括隐藏文件）
3. ls -R 列出当前目录下包含目录和目录中的文件，这个输出会很长（遍历所有的文件和文件夹下的文件及子目录下文件）
4. ls -l 产生长列表的输出，包含了目录中每个文件的更多相关信息
5. ls -l FileName：只输出FileName，过滤输出列表<br>
当不确定文件的名称时，可以采用模式匹配<br>
比如：ls -l my?    (问号代表一个字符)、（*代表多个字符）
##### 处理文件
. 创建文件<br>
    touch test，创建test文件
2. 复制文件<br>
    cp source new
##### 链接文件
![解释](http://i2.muimg.com/567571/b4f811de704f7ebf.png)
test1硬链接指向LinkTest1，test1和LinkeTest1具有相同的索引节点号
test2软连接指向LinkTest2
![实例](http://i2.muimg.com/567571/095f3ca71a060477.png)
![](http://i4.buimg.com/567571/05b3dab4253e4064.png)
##### 重命名文件
cp test1 test2
