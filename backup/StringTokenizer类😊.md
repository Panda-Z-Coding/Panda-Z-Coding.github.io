# **_`StringTokenizer类`_**

>**前言：`StringTokenizer类` 和 `split()` 不同之处在于前者不使用`正则表达式`做分隔标记**

- ### **_`两种构造方法`_**
```java
StringTokenizer(String s)               //为s构造一个分析器,使用默认分隔符 
StringTokenizer(String s,String delim)  //为s构造一个分析器，参数delim的字符的 任意排列 作为分隔标记
```
- ### **_StringTokenizer的操作方法_**

>**我们称StringTokenizer对象是一个字符序列分析器，它封装的数据是若干个单词。<br>所以我们就有两种常见的方法来操作里面的单词**

```java
  .nextToken();       //返回一个单词，并从分析器里删除它
  .hasMoreTokens();   //判断还有没有单词
  .countTokens();     //返回当前的单词数
```



