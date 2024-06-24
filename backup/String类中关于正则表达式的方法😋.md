# **_`String类中关于正则表达式的方法😋`_**

## **字符序列的替换** 
~~~java
public String replaceAll(String regex,String replacement) 
        // 返回一个由replacement匹配regex之后的新String对象
~~~

## **字符序列的分解**
~~~java
public String[] split(String regex); 
        //通过regex的正则表达式来分割当前String对象
~~~

> [!NOTE]
> `split()`方法认为分隔符标记的`左右都是单词`，所以若左边是空字符，那么这个`空字符`算作`第一个单词!`<br>
> 例如:`String str = "公元1949年10月1日是中华人民共和国成立的日子"` <br> 当我们对其使用 `regex = "//D+"` 作为标记符时，数组里面的长度是`4`而不是`3` !

