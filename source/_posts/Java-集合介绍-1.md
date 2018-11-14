---
title: Java - 集合介绍(1)
categories: 技术
date: 2018-11-13 14:59:05
tags: 集合
---



> [Ruheng - 由浅入深理解java集合(一)——集合框架 Collection、Map](https://www.jianshu.com/p/589d58033841) 



#### 集合简介 

- **Java 集合** 大致可分为`Set` , `List` , `Queue` , `Map` 四大体系。
- **Set** 代表 **无序、不可重复** 的集合。
- **List** 代表 **有序、可重复** 的集合。
- **Map** 代表具有 **映射关系** 的集合。
- **Queue** 代表 **队列** 集合。



#### Java 集合和数组的区别 

- **长度** 
  - **数组** 的长度在初始化时指定，意味着只能存 **定长** 的数据。
  - **集合** 可以保存 **数量不确定** 的数据。也可以保存具有**映射关系** 的数据( key - value )。

- **元素类型** 
  - **数组** 既可以保存基本类型的值，也可以保存对象。
  - **集合** 只能保存对象（实际为对象的引用），基本类型必须转换成相应的封装类才可放入集合。



#### 集合类之间的继承关系 

- ![Collection](/images/Collection.png) 
- ![Map](/images/Map.png) 



#### Collection 接口 

- `Collection` 接口是`Set` , `Queue` , `List` 的父接口。

- `Collection` 接口中定义了多种数据操作的方法可供子类进行实现（以下为JDK10版本）。[JDK Collection](https://docs.oracle.com/javase/10/docs/api/java/util/Collection.html) 


| Modifier and Type      | Method                                | Desc                                                         |
| ---------------------- | ------------------------------------- | ------------------------------------------------------------ |
| Boolean                | add(E e)                              | Ensures that this collection contains the specified element (optional operation). |
| boolean                | addAll(Collection<? extends E> c)     | Adds all of the elements in the specified collection to this collection (optional operation). |
| void                   | clear()                               | Removes all of the elements from this collection (optional operation). |
| boolean                | contains(Object o)                    | Returns true if this collection contains the specified element. |
| boolean                | containsAll(Collection<?> c)          | Returns `true` if this collection contains all of the elements in the specified collection. |
| boolean                | equals(Object o)                      | Compares the specified object with this collection for equality. |
| int                    | hashCode()                            | Returns the hash code value for this collection.             |
| boolean                | isEmpty()                             | Returns `true` if this collection contains no elements.      |
| Iterator<E>            | iterator()                            | Returns an iterator over the elements in this collection.    |
| default Stream<E>      | parallelStream()                      | Returns a possibly parallel `Stream` with this collection as its source. |
| boolean                | remove(Object o)                      | Removes a single instance of the specified element from this collection, if it is present (optional operation). |
| boolean                | removeAll(Collection<?> c)            | Removes all of this collection's elements that are also contained in the specified collection (optional operation). |
| default boolean        | removeIf(Predicate<? super E> filter) | Removes all of the elements of this collection that satisfy the given predicate. |
| boolean                | retainAll(Collection<?> c)            | Retains only the elements in this collection that are contained in the specified collection (optional operation). |
| int                    | size()                                | Returns the number of elements in this collection.           |
| default Spliterator<E> | spliterator()                         | Creates a [`Spliterator`](https://docs.oracle.com/javase/10/docs/api/java/util/Spliterator.html) over the elements in this collection. |
| default Stream<E>      | stream()                              | Returns a sequential `Stream` with this collection as its source. |
| Object[]               | toArray()                             | Returns an array containing all of the elements in this collection. |
| <T> T[]                | toArray(T[] a)                        | Returns an array containing all of the elements in this collection; the runtime type of the returned array is that of the specified array. |



- Tips: `iterator()` 方法，当时用`Iterator` 对集合元素进行迭代时，Iterator 并不是把集合元素本身传递给了迭代变量，**而是把集合元素的值传给了迭代变量** 。所以修改迭代变量的值对集合元素本身没有任何影响。

  ```java
  public class IteratorValue {
      public static void main(String[] args){
          List<String> list =Arrays.asList("aaa","bbb","ccc");
          Iterator<String> iterator = list.iterator();
          while(iterator.hasNext()){
              String next = iterator.next();//集合元素的值传给了迭代变量，仅仅传递了对象引用。保存的仅仅是指向对象内存空间的地址
              next ="修改后的";
              System.out.println(next);
              
          }
          System.out.println(list);
      }
  
  }
  
  // 输出结果如下：
  // 修改后的
  // 修改后的
  // 修改后的
  // [aaa, bbb, ccc]
  ```



#### Set 集合

- `Set 集合` 与 `Collection 集合` 基本相同，没有提供额外的方法。
- 只是`Set` 行为略有不同，**不允许包含重复元素** 。
- 如果试图添加两个**相同** 的元素到同一个`Set集合` 中，则添加操作失败，`add()` 方法返回 `false` ，且新元素不会被加入。



#### List 集合

- `List 集合` ，**元素有序、可重复** 。集合中每个元素都有其对应的顺序索引。

- `List` **允许使用重复** 的元素。

- 可以通过索引来访问指定位置的集合元素。

- 默认按元素的添加顺序设置元素的索引。

- `List` 可以使用 `Collection` 接口里的所有方法。而且由于 List 为**有序集合** ，**额外增加** 了一些根据索引来操作集合元素的方法。

  | Modifier and Type | Method                                       | Desc                                                         |
  | ----------------- | -------------------------------------------- | ------------------------------------------------------------ |
  | void              | add(int index, E element)                    | Inserts the specified element at the specified position in this list (optional operation). |
  | boolean           | addAll(int index, Collection<? extends E> c) | Inserts all of the elements in the specified collection into this list at the specified position (optional operation). |
  | E                 | get(int index)                               | Returns the element at the specified position in this list.  |
  | int               | indexOf(Object o)                            | Returns the index of the first occurrence of the specified element in this list, or -1 if this list does not contain the element. |
  | int               | lastIndexOf(Object o)                        | Returns the index of the last occurrence of the specified element in this list, or -1 if this list does not contain the element. |
  | E                 | remove(int index)                            | Removes the element at the specified position in this list (optional operation). |
  | E                 | set(int index, E element)                    | Replaces the element at the specified position in this list with the specified element (optional operation). |
  | List<E>           | subList(int fromIndex, int toIndex)          | Returns a view of the portion of this list between the specified `fromIndex`, inclusive, and `toIndex`, exclusive. |
  | Object[]          | toArray()                                    | Returns an array containing all of the elements in this list in proper sequence (from first to last element). |


