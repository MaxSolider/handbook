# <center>链表

## 定义
链表是一种用于存储数据集合的数据结构。根据元素的组织方式，链表属于线性数据结构，可以按线性次序访问元素。但与数组不同，它并不强制将所有元素连续地存储在一起。<br/>
链表具有以下属性：
* 相邻元素之间通过指针连接；
* 最后一个元素的后继指针值为NULL（这里仅指普通链表，若是循环链表或有环，则不为NULL）；
* 链表长度可以动态变化；
* 链表的空间能够按需分配（直到内存耗尽），没有内存空间的浪费（但链表中的指针需要一些额外的内存开销）

---

## 抽象数据结构
普通链表的数据结构如下图所示：
<img src="https://s2.loli.net/2022/10/07/JPbWmyxwfu6vd8B.png">
<br/>
链表由多个数据结点连接组成，每个数据结点的数据包含自身值，并指向下一个结点。其中，第一个结点称为链表头，最后一个结点称为链表尾。表尾结点的下一个结点指向NULL
<br/>
**链表的主要操作**：
* 插入：插入元素到链表中；
* 删除：移除并返回链表中指定位置的元素。
<br/>

**链表的辅助操作**：
* 删除链表：移除链表中的所有元素（清空链表）；
* 计数：返回链表中元素的个数；
* 查找：寻找从链表表尾开始的第n个结点。

---

## 优缺点
由于链表和数组类似，都可以用于存储数据集合。因此谈论链表的优缺点时，经常拿它与数组做对比。了解链表和数组各自的特点后，才能根据具体场景选择合适的数据结构。<br/>
根据 [02-数组](数据结构与算法/数据结构/01-数组/ReadMe.md) 一节中介绍的数组相关信息，数组的优缺点如下：<br/>
**优点**：
* 简单且易用；
* 访问元素快（常数时间）；
<br/>

**缺点**：
* 大小固定：数组的大小是静态的（需要在使用前指定数组的大小）；
* 需要分配连续的内存空间：数组初始化分配空间时，有时无法分配能存储整个数组的内存空间（当数组规模太大时）；
* 随机插入/删除元素时较复杂：如果要在数组中的给定位置插入元素，可能需要移动存储在数组中的其他元素。尤其是在数组开始位置插入元素时，需要移动原数组中所有的元素。
<br/>

相较于数组，链表的优缺点如下：
<br/>
**优点**：
* 能够在常数时间内扩展（不用移动额外的元素）；
* 无需在提前分配过多空间，只需要在初始时分配一个元素的存储空间。在插入/删除元素时也无需做任何内存重新分配操作。
<br/>

**缺点**：
* 由于链表的存储不连续性，在对链表进行读写时，需要对链表进行遍历找到对应的元素结点。不能做到随机访问。在访问单个元素时的时间开销较大（最差情况下是*O(n)*，而数组的时间开销是*O(1)*）；
* 链表中每个结点的额外指针引用需要额外的内存空间。
<br/>

链表与 [02-数组](数据结构与算法/数据结构/01-数组/ReadMe.md) 以及动态数组的比较如下：
<img src="https://s2.loli.net/2022/10/07/yZxN34RleWz1bUH.png">

---

## 应用场景
常见的链表类型包括 [单向链表](01-单向链表.md) 、 [双向链表](02-双向链表.md) 、 [循环链表](03-循环链表.md) 、 [松散链表](04-松散链表.md) 
<br/>

---

## 常见问题
关于链表的常见问题见 [02-常见问题](数据结构与算法/数据结构/02-链表/02-常见问题/ReadMe.md) 

---