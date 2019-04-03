---
layout: post
title: "javascript常用数组操作方法,包含es6方法"
date: 2018-09-25
description: "javascript常用数组操作方法,包含es6方法"
tag: 技术分享


---   

    前端程序员在日常工作中总是需要跟数组打交道，如何将数组处理成自己想要的样子，就需要对数组的操作方法烂熟于心，这篇分享总结了
    一下JS操作数组的常用方法。


## 一、concat()

    concat() 方法用于连接两个或多个数组。该方法不会改变现有的数组，仅会返回被连接数组的一个副本。

    ```
     var arr1 = [1,2,3];
     var arr2 = [4,5];
     var arr3 = arr1.concat(arr2);
     console.log(arr1); //[1, 2, 3]
     console.log(arr3); //[1, 2, 3, 4, 5]
    ```

## 二、join()

    join() 方法用于把数组中的所有元素放入一个字符串。元素是通过指定的分隔符进行分隔的，默认使用','号分割，不改变原数组。

    ```
    var arr = [2,3,4];
    console.log(arr.join());  //2,3,4
    console.log(arr);  //[2, 3, 4]
    ```

## 三、push()

   push() 方法可向数组的末尾添加一个或多个元素，并返回新的长度。末尾添加，返回的是长度，会改变原数组。

   ```
    var a = [2,3,4];
    var b = a.push(5);
    console.log(a);  //[2,3,4,5]
    console.log(b);  //4
    push方法可以一次添加多个元素push(data1,data2....)
   ```

## 四、pop()

    pop() 方法用于删除并返回数组的最后一个元素。返回最后一个元素，会改变原数组。

    ```
    var arr = [2,3,4];
    console.log(arr.pop()); //4
    console.log(arr);  //[2,3]
    ```

## 五、shift()

    shift() 方法用于把数组的第一个元素从其中删除，并返回第一个元素的值。返回第一个元素，改变原数组。

    ```
    var arr = [2,3,4];
    console.log(arr.shift()); //2
    console.log(arr);  //[3,4]
    ```

## 六、unshift()

    unshift() 方法可向数组的开头添加一个或更多元素，并返回新的长度。返回新长度，改变原数组。

    ```
    var arr = [2,3,4,5];
    console.log(arr.unshift(3,6)); //6
    console.log(arr); //[3, 6, 2, 3, 4, 5]
    tip:该方法可以不传参数,不传参数就是不增加元素。
    ```

## 七、slice()

    返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素。返回选定的元素，该方法不会修改原数组。

    ```
    var arr = [2,3,4,5];
    console.log(arr.slice(1,3));  //[3,4]
    console.log(arr);  //[2,3,4,5]
    ```

## 八、splice()

    splice() 方法可删除从 index 处开始的零个或多个元素，并且用参数列表中声明的一个或多个值来替换那些被删除的元素。如果从 arrayObject 中删除了元素，则返回的是含有被删除的元素的数组。splice() 方法会直接对数组进行修改。

    ```
    var a = [5,6,7,8];
    console.log(a.splice(1,0,9)); //[]
    console.log(a);  // [5, 9, 6, 7, 8]
    var b = [5,6,7,8];
    console.log(b.splice(1,2,3));  //[6, 7]
    console.log(b); //[5, 3, 8]
    ```

## 九、substring() 和 substr()

    相同点：如果只是写一个参数，两者的作用都一样：都是是截取字符串从当前下标以后直到字符串最后的字符串片段。
    substr(startIndex);
    substring(startIndex);

    ```
    var str = '123456789';
    console.log(str.substr(2));    //  "3456789"
    console.log(str.substring(2)) ;//  "3456789"
    ```
    不同点：第二个参数
    substr（startIndex,lenth）： 第二个参数是截取字符串的长度（从起始点截取某个长度的字符串）；
    substring（startIndex, endIndex）： 第二个参数是截取字符串最终的下标 （截取2个位置之间的字符串,‘含头不含尾’）。

    ```
    console.log("123456789".substr(2,5));    //  "34567"
    console.log("123456789".substring(2,5)) ;//  "345"
    ```

## 十、sort 排序

    按照 Unicode code 位置排序，默认升序

    ```
    var fruit = ['cherries', 'apples', 'bananas'];
    fruit.sort(); // ['apples', 'bananas', 'cherries']

    var scores = [1, 10, 21, 2];
    scores.sort(); // [1, 10, 2, 21]
    ```

## 十一、reverse()

   reverse() 方法用于颠倒数组中元素的顺序。返回的是颠倒后的数组，会改变原数组。

   ```
    var arr = [2,3,4];
    console.log(arr.reverse()); //[4, 3, 2]
    console.log(arr);  //[4, 3, 2]
   ```

## 十二、indexOf 和 lastIndexOf

    都接受两个参数：查找的值、查找起始位置
    不存在，返回 -1 ；存在，返回位置。indexOf 是从前往后查找， lastIndexOf 是从后往前查找。

    #### indexOf

    ```
    var a = [2, 9, 9];
    a.indexOf(2); // 0
    a.indexOf(7); // -1

    if (a.indexOf(7) === -1) {
      // element doesn't exist in array
    }
    ```

    #### lastIndexOf

    ```
    var numbers = [2, 5, 9, 2];
    numbers.lastIndexOf(2);     // 3
    numbers.lastIndexOf(7);     // -1
    numbers.lastIndexOf(2, 3);  // 3
    numbers.lastIndexOf(2, 2);  // 0
    numbers.lastIndexOf(2, -2); // 0
    numbers.lastIndexOf(2, -1); // 3
    ```

## 十三、every

    对数组的每一项都运行给定的函数，每一项都返回 ture,则返回 true

    ```
    function isBigEnough(element, index, array) {
      return element < 10;
    }
    [2, 5, 8, 3, 4].every(isBigEnough);   // true
    ```

## 十四、some

    对数组的每一项都运行给定的函数，任意一项都返回 ture,则返回 true

    ```
    function compare(element, index, array) {
      return element > 10;
    }
    [2, 5, 8, 1, 4].some(compare);  // false
    [12, 5, 8, 1, 4].some(compare); // true
    ```

## 十五、filter

    对数组的每一项都运行给定的函数，返回 结果为 ture 的项组成的数组

    ```
    var words = ["spray", "limit", "elite", "exuberant", "destruction", "present", "happy"];

    var longWords = words.filter(function(word){
      return word.length > 6;
    });
    // Filtered array longWords is ["exuberant", "destruction", "present"]
    ```

## 十六、map

    对数组的每一项都运行给定的函数，返回每次函数调用的结果组成一个新数组

    ```
    var numbers = [1, 5, 10, 15];
    var doubles = numbers.map(function(x) {
       return x * 2;
    });
    // doubles is now [2, 10, 20, 30]
    // numbers is still [1, 5, 10, 15]
    ```

## 十七、forEach 数组遍历

    ```
    const items = ['item1', 'item2', 'item3'];
    const copy = [];
    items.forEach(function(item){
      copy.push(item)
    });
    ```

# ES6新增新操作数组的方法

## 1、find()：

    传入一个回调函数，找到数组中符合当前搜索规则的第一个元素，返回它，并且终止搜索。

    ```
    const arr = [1, "2", 3, 3, "2"]
    console.log(arr.find(n => typeof n === "number")) // 1
    ```

## 2、findIndex()：

    传入一个回调函数，找到数组中符合当前搜索规则的第一个元素，返回它的下标，终止搜索。

    ```
    const arr = [1, "2", 3, 3, "2"]
    console.log(arr.findIndex(n => typeof n === "number")) // 0
    ```

## 3、fill()：

    用新元素替换掉数组内的元素，可以指定替换下标范围。

    ```
    arr.fill(value, start, end)
    ```

## 4、copyWithin()：

    选择数组的某个下标，从该位置开始复制数组元素，默认从0开始复制。也可以指定要复制的元素范围。

    ```
    arr.copyWithin(target, start, end)
    const arr = [1, 2, 3, 4, 5]
    console.log(arr.copyWithin(3))
     // [1,2,3,1,2] 从下标为3的元素开始，复制数组，所以4, 5被替换成1, 2
    const arr1 = [1, 2, 3, 4, 5]
    console.log(arr1.copyWithin(3, 1))
    // [1,2,3,2,3] 从下标为3的元素开始，复制数组，指定复制的第一个元素下标为1，所以4, 5被替换成2, 3
    const arr2 = [1, 2, 3, 4, 5]
    console.log(arr2.copyWithin(3, 1, 2))
    // [1,2,3,2,5] 从下标为3的元素开始，复制数组，指定复制的第一个元素下标为1，结束位置为2，所以4被替换成2
    ```

## 5、from

    将类似数组的对象（array-like object）和可遍历（iterable）的对象转为真正的数组

    ```
    const bar = ["a", "b", "c"];
    Array.from(bar);
    // ["a", "b", "c"]

    Array.from('foo');
    // ["f", "o", "o"]
    ```

## 6、of

    用于将一组值，转换为数组。这个方法的主要目的，是弥补数组构造函数 Array() 的不足。因为参数个数的不同，会导致 Array() 的行为有差异。

    ```
    Array() // []
    Array(3) // [, , ,]
    Array(3, 11, 8) // [3, 11, 8]
    Array.of(7);       // [7]
    Array.of(1, 2, 3); // [1, 2, 3]

    Array(7);          // [ , , , , , , ]
    Array(1, 2, 3);    // [1, 2, 3]
    ```

## entries() 返回迭代器：返回键值对

    ```
    //数组
    const arr = ['a', 'b', 'c'];
    for(let v of arr.entries()) {
      console.log(v)
    }
    // [0, 'a'] [1, 'b'] [2, 'c']

    //Set
    const arr = new Set(['a', 'b', 'c']);
    for(let v of arr.entries()) {
      console.log(v)
    }
    // ['a', 'a'] ['b', 'b'] ['c', 'c']

    //Map
    const arr = new Map();
    arr.set('a', 'a');
    arr.set('b', 'b');
    for(let v of arr.entries()) {
      console.log(v)
    }
    // ['a', 'a'] ['b', 'b']
    ```

## 8、values() 返回迭代器：返回键值对的value

    ```
    //数组
    const arr = ['a', 'b', 'c'];
    for(let v of arr.values()) {
      console.log(v)
    }
    //'a' 'b' 'c'

    //Set
    const arr = new Set(['a', 'b', 'c']);
    for(let v of arr.values()) {
      console.log(v)
    }
    // 'a' 'b' 'c'

    //Map
    const arr = new Map();
    arr.set('a', 'a');
    arr.set('b', 'b');
    for(let v of arr.values()) {
      console.log(v)
    }
    // 'a' 'b'
    ```

## 9、keys() 返回迭代器：返回键值对的key

    ```
    //数组
    const arr = ['a', 'b', 'c'];
    for(let v of arr.keys()) {
      console.log(v)
    }
    // 0 1 2

    //Set
    const arr = new Set(['a', 'b', 'c']);
    for(let v of arr.keys()) {
      console.log(v)
    }
    // 'a' 'b' 'c'

    //Map
    const arr = new Map();
    arr.set('a', 'a');
    arr.set('b', 'b');
    for(let v of arr.keys()) {
      console.log(v)
    }
    // 'a' 'b'
    ```

## 10、includes

    判断数组中是否存在该元素，参数：查找的值、起始位置，可以替换 ES5 时代的 indexOf 判断方式。indexOf 判断元素是否为 NaN，会判断错误。

    ```
    var a = [1, 2, 3];
    a.includes(2); // true
    a.includes(4); // false
    ```

    转自[https://segmentfault.com/a/1190000016503330];
