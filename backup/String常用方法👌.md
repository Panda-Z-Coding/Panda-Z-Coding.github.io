# **_String常用方法👌_**

### 「操作String的方法」

```java
public int length()                             // 获取长度
public boolean equals(String s)                 // 查看两个String对象是否相等
public boolean startsWith(String s)             // 前缀是否是s
public boolean endsWith(String s)               // 后缀是否是s
public int compareTo(String s)                  // 通过字典序比较，返回正值、0、负数
public boolean contains(String s)               // 判断String对象里是否含有 s
public int indexOf(String s)                    // 返回首次出现s的位置
public int lastIndexOf(String s)                // 返回最后一次出现s的位置
public String subString(int startpoint)         // 获得一个从该位置到最后的新String对象
public String subString(int start,int end)      // 类似上一个，可以指定最后的位置
public String trim()                            // 获得该对象去除前后空格的新对象

```

### 「String对象和基本数据类型的转换⇄」

 _**String ➡️ 基本型**_

~~~java
public static byte parseByte(String s) throws NumberFormatException
public static short parseShort(String s) throws NumberFormatException
public static long parseLong(String s) throws NumberFormatException
public static float parseFloat(String s) throws NumberFormatException
public static double parseDouble(String s) throws NumberFormatException
~~~

_**基本型 ➡️ String**_

```java
public static String valueOf(_数据类型_ n) //返回一个String对象的引用
```

_**基本类型的进制表示**_

~~~java
public static String toBinaryString(int i) // 返回i的二进制String表示
public static String toOctalString(int i) // 八进制
public static String toHexString(int i) // 十六进制
// int i 或者 long i 都可以
~~~

_**main()方法的参数化💕**_

​      main()方法中的args[] 可以接受从键盘上面键入的字符序列（相当于数组），在运行时可以像以下来键入

> java 主类名 数据1 数据2 ...

### 「对象的String对象表示」

对一个对象调用 toString() 方法会返回String对象的字符序列串

> 一般形式：
>
> 创建对象的类名@对象的引用的字符序列串

🤔要注意的是：toString() 是Object类的方法，是可以被重写的



### 「**String对象与字符数组、字节数组**」

_**String对象与字符数组**_

```java
public viod getChars(int start,int end,char c[],int offset) // 将String对象的字符序列start到end-1列放入数组里
public char[] toCharArray() //全部String的字符序列返回成一个字符数组
```

_**String对象与字节数组**_

>String类中 **String(byte[])** 和 **String(byte[],int offset,int length)** 可以让我们用指定的字节数组的部分或者全部来创建String对象

~~~java
public byte[] getBytes() // 用平台默认的字符编码将String对象放入字节数组用，并返回引用
public byte[] getBytes(String charsetName) // 指定字符编码。。。 
~~~

_**字符序列加密算法**_

>通过**password这个String对象**的**字符序列**作为密码存放在数组里对**另一个sourceString的字符序列**进行**加密**！

~~~java
char[] p = password.toCharArray(); //设p的长度为n
~~~
以下是具体实现
~~~java
public class EncryptAndDecrypt {
    String encrypt(String sourceString,String password) {
        char[] p = password.toCharArray ();
        int n = p.length;
        char[] c = sourceString.toCharArray ();
        int m = c.length;
        for(int k=0;k<m;k++) {
            int mima = c[k] + p[k % n];
            c[k] = (char) mima;
        }
        return new String (c);
    }
    String decrypt(String sourceString, String password) {
        char[] p = password.toCharArray ();
        int n = p.length;
        char[] c = sourceString.toCharArray ();
        int m = c.length;
        for (int k = 0; k < m; k++) {
            int mima = c[k] - p[k % n];
            c[k] = (char) mima;
        }
        return new String (c);
    }
}
---------main类---------
import java. util.Scanner;
public class EncryptAndDecryptMain {
        public static void main( String args[ ]){
            String sourceString= "疯狂星期四";
            EncryptAndDecrypt person =new EncryptAndDecrypt();
            System.out.println("输入密码加密:"+ sourceString);
            Scanner scanner = new Scanner (System.in);
            String password = scanner.nextLine();
            String secret = person. encrypt(sourceString, password);
            System.out.println("密文："+secret);
            System.out.println("输人解密密码");
            String source = person.decrypt(secret, password);
            password = scanner.nextLine();
            System.out.println("明文:"+source);
        }
}
~~~

