#### 一、cat（输出文件全部内容，适用于较小的文本输出）
1. cat -b<br>
   在非空行前加行数

2. cat -n<br>
   输出所有行数

3. cat -s<br>
   不输出多行空行，即将多行空行输出为一行空行

4. cat file1 > file2<br>
   将file1的内容输入到file2内，会覆盖file2的内容</br><br>
   \>代表覆盖写入</br><br>
   \>>代表追加写入</br>

5. cat \<\<EOF > file，向file追加内容（EOF可以为任意内容，代表结束符）<br>
   ```
   heredoc> test1</r><br>
   heredoc> test2<br>
   heredoc> EOF</br><br>
   $ cat file</br><br>
    test1</br><br>
    test2</br>
   ```

6.
#### 二、more（一页一页显示）
1. more -num<br>
   按行数num输出，num是每屏显示的行数

2. more +num<br>
   从第num行开始显示

3. more -f<br>
   计算行数时，以实际上的行数，而非自动换行过后的行数（有些单行字数太长的会被扩展为两行或两行以上）

4. more -p（-c）<br>
   显示下一屏之前先清屏

5. more -s<br>
   文件中连续的空白行压缩成一个空白行显示

6. $ more +/test2 testCat.txt（找到test2第一次出现的位置，从该处前两行开始输出）<br>
    ...跳过</br><br>
    This is a more1.</br><br>
    This is a more test.</br><br>
    This is a test2!</br><br>
    This is a test!</br>
7. more -u 把文件中的下划线去掉

#### 三、less（less 与 more 类似，但使用 less 可以随意浏览文件，而 more 仅能向前移动，却不能向后移动，而且 less 在查看之前不会加载整个文件。）
1. less -i（忽略搜索时的大小写）

2. less -N （显示每行的行号，包括所有空行）

3. less -s （显示连续空行为一行）

4. 使用less输出后，/字符串：向下搜索“字符串”的功能；?字符串：向上搜索“字符串”的功能<br>
    n：重复前一个搜索（与 / 或 ? 有关）</br><br>
    N：反向重复前一个搜索（与 / 或 ? 有关）</br>

5. 