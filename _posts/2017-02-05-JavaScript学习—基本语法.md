---
layout:     post
title:      "JavaScript学习--基本语法"
subtitle:   "JavaScript 变量、赋值、对象和运算符"
date:       2017-02-05 20:00:00
author:     "chengfeir"
header-img: "img/post-bg-js-version.jpg"
catalog: true
tags:
    - JavaScript
    - JS
---

# 代码示例下载

[http://shop.oreilly.com/product/9780596805531.do](http://shop.oreilly.com/product/9780596805531.do)

[http://examples.oreilly.com/9780596805531/](http://examples.oreilly.com/9780596805531/)

# 调试工具

Firefox 上的调试工具 FireBug 
下载地址：[http://getfirebug.com/](http://getfirebug.com/)

# 调试语法

使用console.log()  向控制台输出消息

也可以使用alter() 函数传入一段文本来弹出一个对话框


# 变量和赋值

声明一个变量，JS的变量与OC的变量不同，没有明显的数据类型。

    var x;
    
给变量赋值

    x = 1； //  数字
    x = 0.01; // 整数和实数共用一种数据类型
    x = "hello world"; // 由双引号内的文本构成字符串
    x = 'JavaScript'; // 由单引号内的文本构成字符串
    x = true; // 布尔值
    x = false;
    x = null; // null 空
    x = undefined; // 和null 类似
    
# 对象和数组

以book对象为例

    var book = {
      topic:"JavaScript"，
      fat:true
    };
    
通过"." 或 "[]" 来访问对象属性

    book.topic => "JavaScript"
    book["fat"] => true
    
还可以通过赋值，创建一个新的属性

    book.author = "Flanagan"
    book.contents = {}; // {}是一个空对象，没有属性
    
---

JavaScript 同样支持数组，以数字为索引的列表

    var primes = [2, 3, 5, 7];
    primes[0] => 2 // 数组第一个元素 索引为0
    primes.length => 4 // 数组中的元素个数

通过赋值可以添加元素和改变已有的元素

    primes[4] = 9; // 添加 索引为4 的元素9
    primes[4] = 11; // 通过赋值改变 索引为4 的元素
    
---
数组和对象中都可以包含另一个数组或对象
    
    var points = [  {x:0 ,y:0},
                    {x:1, y:1}
                 ];
    // 具有两个元素的数组，每个数组都是一个对象
    var data = {
        trial1:[[1, 2], [3, 4]],
        trial2:[[2, 3], [4, 5]]
    };// 一个包含两个属性的对象，每一个属性都是数组，数组的元素也是数组
    
# 运算符（operator）

与OC不同的一点，在于 + 可以作字符串连接

    "3" + "2" => "32"
    
    