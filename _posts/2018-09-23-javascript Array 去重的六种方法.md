---
layout: post
title: "javascript 数组去重的六种方法"
date: 2018-09-23
description: "如何使用js对数组进行去重"
tag: 技术分享
---   

    数组去重，一般都是在面试的时候才会碰到，一般是要求手写数组去重方法的代码。如果是被提问到，数组去重的方法有哪些？你能答出其中的10种，面试官很有可能对你刮目相看。
    在真实的项目中碰到的数组去重，一般都是后台去处理，很少让前端处理数组去重。虽然日常项目用到的概率比较低，但还是需要了解一下，以防面试的时候可能回被问到。

    注：写的匆忙，加上这几天有点忙，还没有非常认真核对过，不过思路是没有问题，可能一些小细节出错而已。


## 一、利用ES6 Set去重（ES6中最常用）：

```
function
 unique
(
arr
)

{

return

Array
.
from
(
new

Set
(
arr
))
}
var
 arr
=

[
1
,
1
,
'true'
,
'true'
,
true
,
true
,
15
,
15
,
false
,
false
,

undefined
,
undefined
,

null
,
null
,

NaN
,

NaN
,
'NaN'
,

0
,

0
,

'a'
,

'a'
,{},{}];
console
.
log
(
unique
(
arr
))

//[1, "true", true, 15, false, undefined, null, NaN, "NaN", 0, "a", {}, {}]
```

不考虑兼容性，这种去重的方法代码最少。这种方法还无法去掉“{}”空对象，后面的高阶方法会添加去掉重复“{}”的方法。

## 二、利用for嵌套for，然后splice去重（ES5中最常用）

> 　  function unique(){
> 　  for(let i = 0; i<arr.length; i++){
> 　  for(let j = i+1; j<arr.length; j++){
> 　  if(arr[i] == arr[j]){ //第一个等于第二个， splice方法删除第二个
> 　  arr.splice(j,1);
> 　  j--;
> 　  }
> 　  }
> 　  }
> 　  return arr;
> 　  }
> 　  let arr = [12,32,42,53,123,12,42,123];
> 　  console.log(unique(arr));

双层循环，外层循环元素，内层循环时比较值。值相同时，则删去这个值。

## 三、利用indexOf去重



　