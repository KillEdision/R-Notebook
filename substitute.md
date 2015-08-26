## 将表达式中的内容抽取为字符串
与`quote`的区别在与，`substitute`可以传一个list类型的变量，在list中设定表达式中某个变量的值

### 例子
```r
substitute(expression(a + b), list(a = 1))
substitute(b <- a, list(a = 1))
```
