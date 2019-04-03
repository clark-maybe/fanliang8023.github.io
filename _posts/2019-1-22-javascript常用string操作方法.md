---
layout: post
title: "javascript常用string操作方法"
date: 2019-01-22
description: "javascript常用string操作方法"
tag: 技术分享
---   

    之前整理过常用数组方法，这次来总结一下JS string常用方法。


## 一、charCodeAt(index)

    charCodeAt() 方法返回一个整数，代表指定位置字符的Unicode编码.
    index将被处理字符的从零开始计数的编号，有效值为0到字符串长度减1的数字。

     var str = 'ABC';
     console.log(str.charCodeAt(0))
     //65

## 二、formCharCode(code1,code2)

    formCharCode() 方法从一些Unicode字符串中返回一个字符串，如果没有参数，结果为空字符串.
    

    String.formCharCode(65,66,112);
    //ABp

## 三、charAt(index)

    charAt() 方法返回指定索引位置的字符，如果超出有效范围的索引值返回空字符串

    var str = 'ABC';
    str.charAt(1);
    //B

## 四、slice(start，end)

    slice() 方法返回字符串的片段 start为负，将它作为length+start处理，此处length为字符串的长度
    如果end为负，将它作为length+end处理，此处length为字符串长度

    var str = 'ABCDEFG'
    str.slice(2,4);
    //CD

## 五、substring(start,end)


    var str = 'ABCDEF'
    str.substring(2,4) 或 str.substring(4,2);
    //CD

## 六、substr(start,length)

    start所需的子字符串的起始位置，字符串中的第一个字符的索引为0;
    length在返回的子字符串中应包括的字符个数
    

    var str = 'ABCDEF'
    str.substr(2,4);
    //CDEF

## 七、indexOf(substr,startIndex)

    substr要在string对象内查找的字符串
    startIndex该整数值之处在string对象内进行查找的开始索引位置，如果省略，则查找从字符串的开始处查找

    var str = 'ABCDEF'
    str.indexOf('CD',6)
    //5

## 八、lastIndexOf(substr,startIndex)

    substr要在string对象内查找的子字符串
    startIndex该整数值指出在string对象内进行查找的开始索引位置，如果省略，则查找从字符串的末尾开始

    var str = 'ABCDECDF';
    str.lastIndexOf('CD',6);
    //5

## 九、search(reExp)

    reExp包含正则表达式模式和可用标志的正则表达式对象

    var str = 'ABCDECDF'
    str.search('CD') 或  str.search(/CD/i)
    //2

## 十、concat(string1,string2)

    string1，string2要和所有其他指定的字符串进行连接的string对象或者文字

    var str = 'ABCDEF'
    str.concat('ABCDEF','ABC');
    //ABCDEFABCDEFABC

## 十一、split(separator,limit)

    separator字符串或 正则表达式 对象，它标识了分隔字符串时使用的是一个还是多个字符。如果忽略该选项，返回包含整个字符串的单一元素数组。 
    limit该值用来限制返回数组中的元素个数

    var str = "AA BB CC DD EE FF"; 
    alert(str.split(" "，3));
    //AA,BB,CC

## 十二、toLowerCase()

    该方法返回一个字符串，该字符串中的字母被转换成小写

    var str = 'ABCabc'
    str.toLowerCase();
    //abcabc


## 十三、toUpperCase()

    该方法返回一个字符串，该字符串中的字母被转换成大写

    var str = 'ABCabc'
        str.toUpperCase();
        //ABCABC


在文章的结尾，我要说一句...


**鑫哥牛逼！**

[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)
