# **_`Scanner类 🤨`_**

> **我们可以用`Scanner`对象解析字符序列中的单词，从而解析出程序需要的数据**
>

- **Scanner对象**
  
```java
String GDUFE = "I love GDUFE";
//利用scanner解析GDUFE中的单词
Scanner scanner = new Scanner(GDUFE);
//创建Scanner对象
```

- **Scanner对象方法**
  - **`.useDelimiter(正则表达式); // 将正则表达式作为分隔标记`** 
  - **`.next(); // 返回一个单词`**
  - **`.hasNext() // 判断还有无单词`**
  - **`.nextInt(); 和 .nextDouble(); // 对于数字类型的单词，用这两个比较妥当；当然如果不是数字类型就不要作死用这个`**
  - Why? 会发生 **_`InputMismatchException`_** 异常，所以记得放入**try-catch**语句里



> [!IMPORTANT]
> - **`🤔所以？这个Scanner和StringTokenizer有什么区别？？`**
>   - **我们先从他们各自的工作原理看起：**
>       - **`StringTokenizer` 是把分解出来的单词全部放入对象实体中😟**
>       - **`Scanner` 是仅存放咋样获取单词分隔标记😲**
>   - **不同的处理各有什么好处？**
>       - **`StringTokenizer` 以空间换速度**
>       - **`Scanner` 以速度换空间**
>       - **大文件解析可以用`Scanner`，而想要快速知道单词数目得用`StringTokenizer`**
>   - **`Scanner`中没有`countTokens()`这样的函数，因为实体里面不是单词，想知道单词数量必须一个个取出来**