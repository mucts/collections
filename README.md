<p align="center"><img src="https://images.mucts.com/image/exp_def_white.png" width="400"></p>
<p align="center">
    <a href="https://scrutinizer-ci.com/g/mucts/collections"><img src="https://scrutinizer-ci.com/g/mucts/collections/badges/build.png" alt="Build Status"></a>
    <a href="https://scrutinizer-ci.com/g/mucts/collections"><img src="https://scrutinizer-ci.com/g/mucts/collections/badges/code-intelligence.svg" alt="Code Intelligence Status"></a>
    <a href="https://scrutinizer-ci.com/g/mucts/collections"><img src="https://scrutinizer-ci.com/g/mucts/collections/badges/quality-score.png" alt="Scrutinizer Code Quality"></a>
    <a href="https://packagist.org/packages/mucts/collections"><img src="https://poser.pugx.org/mucts/collections/d/total.svg" alt="Total Downloads"></a>
    <a href="https://packagist.org/packages/mucts/collections"><img src="https://poser.pugx.org/mucts/collections/v/stable.svg" alt="Latest Stable Version"></a>
    <a href="https://packagist.org/packages/mucts/collections"><img src="https://poser.pugx.org/mucts/collections/license.svg" alt="License"></a>
</p>

# Collection #

> `Collection`类提供一个便捷的操作数组的封装。

## 创建一个新的集合 ##

一个集合可以使用`collect()`帮助函数基于一个数组被创建 或者直接通过`MuCTS\Collections\Collection`类实例化。

- 一个非常简单的使用 collect() 帮助函数的示例：

```php
$newCollection = collect([1, 2, 3, 4, 5]);
```

