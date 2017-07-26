#### mv
1. 将file 重命名为file.txt
```
root at wangchao-virtual-machine in /home/wangchao/Learn
$ ls -l
总用量 12
-rw-r--r-- 1 root     root      24 7月  24 22:42 file
-rw-r--r-- 1 root     root     481 7月  24 22:16 testCat2.txt
-rw-rw-r-- 1 wangchao wangchao 295 7月  25 21:21 testCat.txt

root at wangchao-virtual-machine in /home/wangchao/Learn 
$ mv file file.text

root at wangchao-virtual-machine in /home/wangchao/Learn
$ ls -l
总用量 12
-rw-r--r-- 1 root     root      24 7月  24 22:42 file.text
-rw-r--r-- 1 root     root     481 7月  24 22:16 testCat2.txt
-rw-rw-r-- 1 wangchao wangchao 295 7月  25 21:21 testCat.txt</br>
```
2. 将文件file.txt移至TEST
```
root at wangchao-virtual-machine in /home/wangchao/Learn
$ ls -l | grep '^d'
drwxr-xr-x 2 root     root     4096 7月  26 21:45 TEST

root at wangchao-virtual-machine in /home/wangchao/Learn
$ ls -l
总用量 16
-rw-r--r-- 1 root     root       24 7月  24 22:42 file.text
drwxr-xr-x 2 root     root     4096 7月  26 21:45 TEST
-rw-r--r-- 1 root     root      481 7月  24 22:16 testCat2.txt
-rw-rw-r-- 1 wangchao wangchao  295 7月  25 21:21 testCat.txt

root at wangchao-virtual-machine in /home/wangchao/Learn 
$ mv file.text TEST

root at wangchao-virtual-machine in /home/wangchao/Learn
$ ls -l
总用量 12
drwxr-xr-x 2 root     root     4096 7月  26 21:51 TEST
-rw-r--r-- 1 root     root      481 7月  24 22:16 testCat2.txt
-rw-rw-r-- 1 wangchao wangchao  295 7月  25 21:21 testCat.txt

root at wangchao-virtual-machine in /home/wangchao/Learn
$ cd TEST

root at wangchao-virtual-machine in /home/wangchao/Learn/TEST
$ ls -l
总用量 4
-rw-r--r-- 1 root root 24 7月  24 22:42 file.text
```
3. mv -t 目录 文件1 文件2（移动多个文件）
```
root at wangchao-virtual-machine in /home/wangchao/Learn
$ ls -l
总用量 12
drwxr-xr-x 2 root     root     4096 7月  26 21:51 TEST
-rw-r--r-- 1 root     root      481 7月  24 22:16 testCat2.txt
-rw-rw-r-- 1 wangchao wangchao  295 7月  25 21:21 testCat.txt

root at wangchao-virtual-machine in /home/wangchao/Learn
$ mv -t TEST testCat2.txt testCat.txt

root at wangchao-virtual-machine in /home/wangchao/Learn
$ ls -l
总用量 4
drwxr-xr-x 2 root root 4096 7月  26 22:06 TEST

root at wangchao-virtual-machine in /home/wangchao/Learn
$ cd TEST

root at wangchao-virtual-machine in /home/wangchao/Learn/TEST
$ ls -l
总用量 12
-rw-r--r-- 1 root     root      24 7月  24 22:42 file.text
-rw-r--r-- 1 root     root     481 7月  24 22:16 testCat2.txt
-rw-rw-r-- 1 wangchao wangchao 295 7月  25 21:21 testCat.txt
```
4. mv -i （如果移动目录下存在同名文件，提示是否覆盖）
5. mv dir1 dir2 （目录的移动）
6. mv -b备份
```
root at wangchao-virtual-machine in /home/wangchao/Learn/TEST
$ mv testCat.txt -b testCat2.txt

root at wangchao-virtual-machine in /home/wangchao/Learn/TEST
$ ls -l
总用量 8
-rw-r--r-- 1 root     root       0 7月  26 22:08 file.txt
-rw-rw-r-- 1 wangchao wangchao 295 7月  25 21:21 testCat2.txt
-rw-r--r-- 1 root     root     481 7月  24 22:16 testCat2.txt~

```