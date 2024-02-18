# 集合类总结

#### **Author : JunJie**



[TOC]



## 集合概述

> Java 集合， 也叫作容器
>
> 主要由**两大接口**派生而来
>
> - **Collection接口**
>   - 主要用于存放**单一元素** [单列]
> - **Map接口**
>   - 主要用于存放**键值对** [双列]

```java 
集合类
  |---Collection
  |       |--List
  |       |--Set
  |       |--Queue
  |---Map
```





### 1.集合框架

<img src="D:\AWD\Note\JavaSE_Note\other\集合类总结\img\Collection-relationship.png" style="zoom: 50%;" />

​																		注：图中只列举了主要的继承派生关系，并没有列举所有关系



### 2.为什么要使用集合？

当我们需要存储一组类型相同的数据时，数组是最常用且最基本的容器之一。

但在实际开发中，存储的数据 ：**1.数量不确定 2.数据类型多种多样** 

这时，Java 集合就派上用场了。

**Java 集合框架**中的各种集合类和接口**可以存储不同类型和数量的对象**，同时还具有**多样化的操作方式**。

相较于数组，Java 集合的优势在于它们的大小可变、支持泛型、具有内建算法等。

总的来说，Java 集合提高了数据的存储和处理灵活性



### 3.如何选用集合？

------

根据集合的特点选择：

- 需要根据 **key - vaule** 获取到元素值时就选用 **`Map`** 接口下的集合
  - **不需要排序时**就选择 **`HashMap`** **[高频使用]**
  - **需要排序时**选择 `TreeMap`
  - 如果需要**保持插入顺序或者访问顺序**，可以选择使用 `LinkedHashMap`
  - 需要保证**线程安全**就选用 `ConcurrentHashMap`。
  - `hashtable` 是线程安全的，但不建议使用 [ 推荐使用 `ConcurrentHashMap` 替代 `Hashtable` ]
- 只需要**存放元素值**时，就选择实现**`Collection`** 接口的集合
  - 需要 **有序**的集合，并且**可**能包含**重复**元素时，使用 List。
    - **ArrayList** : 需要**频繁**地**访问** [数组]
    - LinkedList : 需要**频繁地插入和删除** [链表]
    - Vector,Stack 不建议使用
  - 需要 **保证元素唯一**[不重复]，并且不在意元素的顺序[无序]时，使用 Set。
    - 不需要保证元素的顺序，并且希望在添加、删除和查询元素时具有**最佳性能**，可以选择使用 HashSet。
    - 需要**保持元素的插入顺序**，可以选择使用 LinkedHashSet。
    - 需要对元素进行**排序**，可以选择使用 TreeSet
  - 需要 队列 / 栈时，使用 Queue。



实际开发时，主要用法 [ 99%的使用场景 ]：

``` java
List<Integer> list = new ArrayList<>();		//底层是数组，自动扩容
Set<String> set = new HashSet<>();			//主要用来去除重复元素 [底层是HashMap]
Map<String,String> map = new HashMap<>();	//什么是key，什么是vaule？
```

遍历





### 4.集合框架底层数据结构总结

------

 **`Collection` 接口下面的集合**

**List**

- `ArrayList`：`Object[]` 数组。
- `LinkedList`：双向链表
- `Vector`：`Object[]` 数组。

**Set**

- `HashSet`(无序，唯一): 基于 `HashMap` 实现的，底层采用 `HashMap` 来保存元素。
- `LinkedHashSet`: `LinkedHashSet` 是 `HashSet` 的子类，并且其内部是通过 `LinkedHashMap` 来实现的。
- `TreeSet`(有序，唯一): 红黑树(自平衡的排序二叉树)。

**Queue**

- `ArrayDeque`: 循环数组

------

 **`Map` 接口下面的集合**

- **HashMap : 数组 + 链表 + 红黑树**
- LinkedHashMap : 数组 + 双向链表 + 红黑树
- Hashtable : 数组+链表
- TreeMap : 红黑树（自平衡的排序二叉树）



### 5.List, Set, Queue, Map 四者的区别？

------

`List`  (对付顺序的好帮手) : 存储的元素是有序的、可重复的。

`Set`  (注重独一无二的性质) : 存储的元素不可重复的。

`Queue`  (实现排队功能的叫号机) : 按特定的排队规则来确定先后顺序，存储的元素是有序的、可重复的。

`Map`  (用 key 来搜索的专家) : 使用键值对（key-value）存储，key 是无序的、不可重复的，value 是无序的、可重复的，每个键最多映射到一个值。





## List





## Set





## Queue





## Map

