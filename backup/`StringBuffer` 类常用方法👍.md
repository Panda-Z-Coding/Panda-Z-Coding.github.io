### `StringBuffer`

--------------

1. **构造方法**
   - `StringBuffer()`：创建一个空的 `StringBuffer` 对象。
   - `StringBuffer(int capacity)`：创建指定容量的 `StringBuffer` 对象。
   - `StringBuffer(String str)`：创建一个包含指定字符串的 `StringBuffer` 对象。

2. **追加方法**
   - `append(String str)`：将指定的字符串追加到此字符序列。
   - `append(char c)`：将指定的字符追加到此字符序列。
   - `append(int i)`：将指定的整数追加到此字符序列。
   - `append(Object obj)`：将指定的对象的字符串表示形式追加到此字符序列。

3. **插入方法**
   - `insert(int offset, String str)`：在指定位置插入指定的字符串。
   - `insert(int offset, char c)`：在指定位置插入指定的字符。
   - `insert(int offset, int i)`：在指定位置插入指定的整数。
   - `insert(int offset, Object obj)`：在指定位置插入指定的对象的字符串表示形式。

4. **删除方法**
   - `delete(int start, int end)`：删除此序列的子字符串中的字符。
   - `deleteCharAt(int index)`：删除指定位置的字符。

5. **替换方法**
   - `replace(int start, int end, String str)`：使用指定的字符串替换此序列的子字符串中的字符。

6. **反转方法**
   - `reverse()`：将此字符序列用其反转形式取代。

7. **获取长度和容量**
   - `length()`：返回此字符序列的长度。
   - `capacity()`：返回当前容量。

8. **获取子串**
   - `substring(int start)`：返回一个新的 `String`，它包含此字符序列当前包含的字符的子序列。
   - `substring(int start, int end)`：返回一个新的 `String`，它包含此序列当前包含的字符的子序列。

9. **设置字符或字符串**
   - `setCharAt(int index, char ch)`：将指定索引处的字符设置为 `ch`。