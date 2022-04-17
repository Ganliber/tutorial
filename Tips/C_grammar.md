# C grammar addition

***

[TOC]



## 文件读写

> C语言中对于文件的读写主要分为五类，详见[C语言文件读写](https://blog.csdn.net/qq_29769263/article/details/85329099?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522164976767816780366593468%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=164976767816780366593468&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-85329099.142^v7^article_score_rank,157^v4^control&utm_term=C%E8%AF%AD%E8%A8%80%E8%AF%BB%E5%86%99%E6%96%87%E4%BB%B6&spm=1018.2226.3001.4187)

1. 字符的读写：`fgetc()`函数和`fputc()`函数
2. 字符串的读写：`fgets()`函数和`fputs()`函数
3. 数据块的读写：`fread()`函数和`fwrite()`函数
4. 格式化读写：`fscanf()`函数和`fprintf()`函数
5. 随机读写函数：`fseek()`、`rewind()`、`ftell()`

### Char

* `fputc()`函数
  format : fputc(c,fp);

  function : 用来将一个字符写入到文件中。

  Input : 在格式中fp是已经定义的文件指针变量；c为要写入的字符，可以是字符常量或字符型变量，该函数有返回值

  return : 如果执行成功，返回写入的字符；否则，返回EOF,（EOF是C语言编译系统定义的文本文件结束标志，其值为-1，十六进制表示为0xff，在stdio.h中定义），表示写操作失败。

* `fgetc()`

  format : fgetc(c,fp)

  function : 用来从指定的文本文件中读取一个字符。

  Input : fp为文件指针，c为要写入的字符。该函数的功能是从指定的文件中读取一个字符,并赋值给字符型变量c。 

  return : 读取成功返回读取字符，读取错误或遇到结束标志EOF，返回EOF。

### String

* `fputs()`

  format : fputs(s,fp);

  function : 用来将一个字符串写入指定的文本文件。

  Input : fp为文件指针，s可以是字符数组名，字符型指针变量或字符串常量。该函数的功能是将字符串s写入由fp指向的文件中，字符串末尾的‘\0’字符不允写入。

  return : 执行成功，返回所写的最后一个字符；否则，返回EOF。

* `fgets()`

  format : fgets(s,n,fp);

  function : 用于从指定的文件中读一个字符串到字符数组中。

  Input : s可以是字符型数组名或字符串指针,n是指定读入的字符个数；fp为文件指针。n是一个正整数，表示从文件中最多读取n-1个字符，并将字符串指针s定位在读入的字符串首地址。fgets()函数从文件中读取字符直到遇到回车符或EOF为止，函数会在最后一个字符后加上字符串结束标志’\0’；若有EOF，则不予保留。

  return : 该函数如果执行成功，返回读取字符串；如果失败，则返回空指针NULL，这时，s中的内容不确定。

### Format

* `fprintf()`
  format : fprintf(fp, format, arg1, arg2,….,argn);

  function : fprintf()用来将输出项按指定的格式写入指定的文本文件中.

  Input : 格式化规定与printf()函数功能相似，所不同的只是fprintf()函数是将输出的内容写入文件中，而printf()函数则是在屏幕输出。其中，fp为文件指针，format为指定的格式控制字符串；arg1~argn为输出项，可以是字符、 字符串或各种类型的数值。该函数的功能是按格式控制字符串format给定的格式，将输出项arg1,arg2,…..,argn的值写入fp所指向的文件中。

  return : 如果函数执行成功，返回实际写入文件的字符个数；若出现错误，返回负数。


  other : fprintf()函数与printf函数一样的用法，只是在前面增加了一个发fp参数，即需要传入文件指针，printf是把字符按照格式打印到屏幕上，而fprintf是按照格式打印到文本中。

* `fscanf()`

  format : fscanf(fp,format,arg1,arg2,…..,argn);

  function : fscanf()用来按规定的格式从指定的文本文件中读取数据。它与scanf()函数的功能相似，都是按规定的格式读数据的函数，只是fscanf()函数读的对象不是键盘区，而是文件。

  Input : fp为文件指针，format为指定的格式控制字符串；arg1~argn为输入项的地址。该函数的功能是从文件指针fp所指的文本文件中读取数据，按格式控制字符串format给定的格式赋予输入项arg1,arg2,…..,argn中。

  return : 如果该函数执行成功，返回读取项目个数；如果遇到文件末尾，返回EOF;如果赋值失败，返回0.
  



















