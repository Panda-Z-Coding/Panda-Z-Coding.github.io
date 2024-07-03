<iframe style='border-radius:12px' src='https://open.spotify.com/embed/track/0U3fV7K4WFfVRgLGEAKh3g?utm_source=generator' width='100%' height='152' frameBorder='0' allowfullscreen='' allow='autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture' loading='lazy'></iframe>
# **`I/O流-简易版😉`**

> 😋Live is suck but you will like it

### 1. File类 - _用来获取文件信息_
- **获取文件属性**：
  - `getName()`：获取文件名。
  - `getPath()`：获取文件路径。
  - `getAbsolutePath()`：获取文件的绝对路径。
  - `getParent()`：获取文件的父目录。
  - `exists()`：检查文件是否存在。
  - `canRead()`: 是否可读。
  - `canWrite()`: 是否可写。
  - `isHidden()`: 文件是否为隐藏文件。
  - `isFile()`：检查是否为文件。
  - `isDirectory()`：检查是否为目录。
  - `length()`：获取文件大小。
  - `lastModified()`：获取文件最后修改时间。

- **目录相关方法**：
  - `boolean mkdir()`：创建单个目录,创建成功返回true，false表示已经有了
  - `String[] list()`：列出目录下的文件和目录名。
  - `File[] listFiles()`：用File对象的形式分会目录下的全部文件。

- **文件的创建和删除**：
  - `createNewFile()`：对 **`文件对象`** 调用创建新文件。
  - `delete()`：删除文件或空目录。

### 2. 文件字节输入流（FileInputStream）
- 用于从文件中 **`读取`** 字节数据。
- 常用方法：
  - `read()`：读取单个字节。
  - `read(byte[] b)`：将数据读取到字节数组中。
  - `available()`：返回可读取的字节数。
  - `close()`：关闭流。

### 3. 文件字节输出流（FileOutputStream）
- 用于 **`向文件中写入`** 字节数据。
- 常用方法：
  - `write(int b)`：写入单个字节。
  - `write(byte[] b)`：写入字节数组。
  - `write(byte[] b, int off, int len)`：off是偏移量，len是长度
  - `close()`：关闭流。
  - `flush()`：刷新流，将缓冲区的数据写入文件。

### 4. 文件字符输入输出流（FileReader/FileWriter）

- **FileReader** 用于从文件中读取字符数据。
  - `FileReader(String fileName)`：创建一个新的 FileReader，给定要读取的文件名。
  - `FileReader(File file)`：创建一个新的 FileReader，给定要读取的 File 对象。
  - `int read()`：读取单个字符，返回一个整数，表示字符的 Unicode 值，如果已到达流的末尾，则返回 -1。
  - `int read(char[] cbuf)`：将字符读入数组，返回读取的字符数，如果已到达流的末尾，则返回 -1。
  - `void close()`：关闭该流并释放与之关联的所有资源。

- **FileWriter** 用于向文件中写入字符数据。
  - `FileWriter(String fileName)`：创建一个新的 FileWriter，给定要写入的文件名。
  - `FileWriter(File file)`：创建一个新的 FileWriter，给定要写入的 File 对象。
  - `FileWriter(String fileName, boolean append)`：创建一个新的 FileWriter，给定要写入的文件名，并指定是否追加写入。
  - `void write(int c)`：写入单个字符。
  - `void write(char[] cbuf)`：写入字符数组。
  - `void write(String str)`：写入字符串。
  - `void write(char[] cbuf, int off, int len)`：off是偏移量，len是长度
  - `void write(String str, int off, int len)`：同上
  - `void flush()`：刷新该流的缓冲，将缓冲数据写入文件。
  - `void close()`：关闭此流，但要先刷新它。

### 5. 缓冲流（BufferedInputStream/BufferedOutputStream, BufferedReader/BufferedWriter）
- 提供缓冲功能，减少实际的物理读写次数，提高效率。
- 常用方法：
  - `read()`/`write()`：读写数据。
  - `readLine()`：读取一行文本。
  - `newLine()`：写入一个行分隔符。
  - `close()`：关闭流。

### 6. 随机流（RandomAccessFile）
- 支持随机访问文件，可以在文件的任何位置 **`读写`** 数据。
- 常用方法：
  - `read()`/`write()`：读写数据。
  - `seek(long pos)`：设置文件指针偏移量。
  - `getFilePointer()`：获取文件指针当前位置。
  - `close()`：关闭流。

### 7. 数组流（ByteArrayInputStream/ByteArrayOutputStream）
- 用于操作字节数组，不涉及文件系统。
- 常用方法与文件字节流类似。

### 8. 数据流（DataInputStream/DataOutputStream）
- 用于读写基本数据类型的数据。
- 常用方法：
  - `readBoolean()`/`writeBoolean(boolean v)`：读写布尔值。
  - `readInt()`/`writeInt(int v)`：读写整数。
  - `close()`：关闭流。

### 9. 对象流（ObjectInputStream/ObjectOutputStream）
- 用于序列化和反序列化对象。
- 常用方法：
  - `readObject()`：读取对象。
  - `writeObject(Object obj)`：写入对象。
  - `close()`：关闭流。

在使用这些流时，需要注意流的 **打开和关闭** ，以及异常处理。通常使用`try-with-resources`语句来自动关闭流，确保资源的正确释放。