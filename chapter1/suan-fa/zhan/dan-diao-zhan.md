# 单调栈

## 用途

> * 求解数组中元素右边第一个比它小的元素的下标，从前往后，构造单调递增栈
>
> * 求解数组中元素右边第一个比它大的元素的下标，从前往后，构造单调递减栈
>
> * 求解数组中元素左边第一个比它大的元素的下标，从后往前，构造单调递减栈
>
> * 求解数组中元素左边第一个比它小的元素的下标，从后往前，构造单调递增栈

### 单调递增栈

> ```
> for(int i = 0; i < T.size(); i++){
>   while(! stk.empty() && stk.top() > T[i]){
>     ​stk.pop();
>   }
>   stk.push(A[i]);
> }
> ```

### 单调递减栈

> ```
> for(int i = T.size() - 1; i >= 0; i--){
>   while(! stk.empty() && T[i] >= stk.top()){
>     stk.pop();
>   }         
>   stk.push(i);
> }
> ```

## 题目

> * 每日温度 [https://leetcode-cn.com/problems/daily-temperatures/](#)



