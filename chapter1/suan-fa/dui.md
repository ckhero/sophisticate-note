# 堆

## 资料

> [https://www.jianshu.com/p/6b526aa481b1](https://www.jianshu.com/p/6b526aa481b1)

## 简述

> 用数组来实现的二叉树，没有使用父指针和子指针

## 堆属性

> 分为最大堆和最小堆
>
> * 最大堆，每一个父节点的值都比子节点大
> * 最小堆，每一个父节点的值都比子节点小

## 公式

> ```
> //i代表数组中的索引
> parent(i) = floor((i - 1)/2)
> left(i)   = 2i + 1
> right(i)  = 2i + 2
> ```

## 用途

> * 构建优先队列
>
> * 支持堆排序
>
> * 快速找出一个集合中的最小值（或者最大值）

## 最小堆题目

> * 数组中d额第k个最大元素 [https://leetcode-cn.com/problems/kth-largest-element-in-an-array/](https://leetcode-cn.com/problems/kth-largest-element-in-an-array/)
>
> * 前K个高频元素 [https://leetcode-cn.com/problems/top-k-frequent-elements/](https://leetcode-cn.com/problems/top-k-frequent-elements/)



