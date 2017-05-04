##### awk
1. 使用数据字段变量
$0代表整个文本行，$1代表文本行中的第一个数据字段,以此类推
[root@bogon LearnSed]# echo "This is a test" | awk '{$4="Test"; print $0}'
This is a Test
2. 处理数据前运行脚本
[root@bogon LearnSed]# awk 'BEGIN {print "start"}{print $0}' test1 
start
This is a Test1!
This is a Test2!
This is a Test3!
This is a Test4!
This is a Test5!
This is a Test6!
This is a Test7!
3. 处理数据后运行脚本
[root@bogon LearnSed]# awk 'BEGIN {print "start"}{print $0} END {print "end"}' test1 
start
This is a Test1!
This is a Test2!
This is a Test3!
This is a Test4!
This is a Test5!
This is a Test6!
This is a Test7!




end
