# Python算法实例精简
## 链表（link）
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None 
        return
    def has_value(self, value):
        if self.data == value:
            return True
        else:
            return False
#! 定义一个值为 1 的节点
#? Node(1)

#链表类
'''
head -> 头节点
tail -> 尾节点
length -> 长度
'''

'''
isempty()
add_Node(self, item)
insert_node(self, index, data)
delete_node_byid(self, item_id)
find_node(self, value)
print_link(self)
'''

class singlelink:
    def __init__(self):
        self.head = None
        self.tail = None
        self.length = 0
        return
    def isempty(self):
        return self.length == 0
    #? 尾部添加节点
    def add_Node(self, item):
        if not isinstance(item, Node): #! isinstance(对象, 类)检查是否是这个类
            item = Node(item)
        if self.head is None:
            self.head = item
            self.tail = item
        else:
            self.tail.next = item
            self.tail = item
        self.length += 1
        return
    #? 插入节点
    def insert_node(self, index, data):
        if self.isempty():  # 如果链表为空
            if index == 0:  # 在索引0的位置插入节点
                self.head = Node(data)
                self.tail = self.head
            else:
                print("error: out of index")
        else:  # 如果链表不为空
            if index < 0 or index > self.length:  # 如果插入位置不在链表范围内
                print("error: out of index")
            else:
                item = Node(data)  # 创建节点
                if index == 0:  # 如果插入位置为链表头部
                    item.next = self.head
                    self.head = item
                else:
                    node = self.head
                    j = 0
                    while j < index - 1 and node.next:  # 找到插入位置的前一个节点
                        node = node.next
                        j += 1
                    item.next = node.next  # 在插入位置插入节点
                    node.next = item
                self.length += 1  # 链表长度加1

    #? 通过索引删除节点
    def delete_node_byid(self, item_id):
        if self.isempty():  # 如果链表为空
            print("error: link is empty")
            return

        id = 1
        current_node = self.head  # 当前节点
        previous_node = None

        while current_node:  # 当当前节点不为空时
            if id == item_id:
                if previous_node is not None:
                    previous_node.next = current_node.next
                else:
                    self.head = current_node.next  # 如果上一个节点是空的（也就是link是空的）
                    return
            previous_node = current_node
            current_node = current_node.next  # 这两行是为了把指针向下一个节点移动
            id += 1

        self.length -= 1

    #? 通过数值在链表中找到节点
    def find_node(self, value):
        current_node = self.head
        node_id = 1
        results = [] # 可能存在多个一样的值
        while current_node is not None:
            if current_node.has_value(value):
                results.append(node_id)
            current_node = current_node.next
            node_id += 1
        return results
    #? 按顺序输出链表
    def print_link(self):
        current_node = self.head
        while current_node is not None:
            print(current_node.data,end=' ')
            current_node = current_node.next
        return

node1 = Node(1)
node2 = Node(2)
node3 = Node(3)
print('-----------')
link = singlelink()
for node in [node1,node2,node3]:
    link.add_Node(node)
link.print_link()      
print(f"链表长度为{link.length}")
print('-----------')
link.insert_node(2,6)
link.print_link()
print(f"链表长度为{link.length}")
link.delete_node_byid(1)
link.print_link()
print(f"链表长度为{link.length}")
link.add_Node(Node(2))
link.print_link()
print()
print(f"find 2 element : {link.find_node(2)}")
print('-----------')
```
- 运行⬇️
![Snipaste_2024-10-02_17-46-25](https://github.com/user-attachments/assets/8c39ccdc-ab3b-4eed-ab5e-4a1dbe3fc5e1)

