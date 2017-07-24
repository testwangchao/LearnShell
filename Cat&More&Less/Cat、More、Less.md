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
   heredoc> test1</br><br>
   heredoc> test2<br>
   heredoc> EOF</br><br>
   $ cat file</br><br>
    test1</br><br>
    test2</br>

#### 二、more（一页一页显示）
1. more -num<br>
   按行数num输出，num是需要显示的行数

2. more +num<br>
   从第num行开始显示

3. more -f<br>
   计算行数时，以实际上的行数，而非自动换行过后的行数（有些单行字数太长的会被扩展为两行或两行以上）

4. more -p<br>
   显示下一屏之前先清屏

5. more -s<br>
   文件中连续的空白行压缩成一个空白行显示

6.