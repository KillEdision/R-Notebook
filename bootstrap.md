## 非参数bootstrap抽样

### 实现代码
```r
"bootstrap"<- function(x,nboot,theta,...) {
    call <- match.call()
    n <- length(x)
    bootsam<- matrix(sample(x,size=n*nboot,replace=TRUE),nrow=nboot)
    thetastar <- apply(bootsam,1,theta,...)
    return(list(bootsam=bootsam，thetastar=thetastar,call=call))
}
```
### 参数
+ x
用于抽样的样本
+ nboot
抽样次数
+ theta
施加于bootstrap抽样生成的数据集上的函数

### 例子
```r
x <- c(136.3,136.6,135.8,135.4,134.7,135.0,134.1,143.3,147.8,148.8,134.8,135.2,134.9,146.5,141.2,135.4,134.8,135.8,135.0,133.7,134.4,134.9,134.8,134.5,134.3,135.2)
theta <- function(x){median(x)}
bootstrap(x = x,nboot = 10000,theta = theta2)
```
