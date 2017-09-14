#### xargs

- -n 指定每行最大的参数数量n
  ```
  $ cat example.txt | xargs -n 3
  ```
    1 2 3

    4 5 6

    7 8 9

    10 11 12


- 用-d选项为输入指定一个定制的定界符
  ```
  $ echo "splitXsplitXsplitXsplit" | xargs -d X
  ```

   split split split split

-