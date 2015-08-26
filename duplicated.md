## 判断是否为重复元素

### 代码
```r
x <- sample(1:3,9,replace = TRUE)
duplicated(x,fromLast = FALSE)
any(duplicated(x))
```

### 解释
因为`x`通过有放回抽样生成，所以`x`向量中有某些元素是重复了的，`duplicated`判断向量中哪些是复制了前面的元素

### 参数
+ x 
用于判断的向量
+ fromLast
是否逆序判断
