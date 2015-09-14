## replicate
### 用法
```r
replicate(n,expr)
# 将expr重复执行n次，返回列表
```

## <<-
### 用法
```
a<0
for(i in 1:10){
  for(j in 1:10){
    a<<-i*j
  }
}
print(a)
# a=3 在循环中向外层变量赋值
```

## is.finite
### 用法
```r
x<-Inf
is.finite(x)
# 判断变量是否是有界的
```

## postscript
### 用法
```r
postscript(file='D:/')
plot(3,3)
dev.off()
## 生成跨平台的图像文件
```

## pretty
###
```r
pretty(x = 1:10,n = 20)
#生成美化的断点，将1:10切分为20个离散的数
```
