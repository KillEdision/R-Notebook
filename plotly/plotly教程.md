## [Plotly for R](https://plot.ly/r/getting-started/)
### 安装
plotly is not (yet) available on CRAN, but you can install it via devtools:
```r
install.packages("viridis") # dependency
install.packages("devtools")
devtools::install_github("ropensci/plotly")
```
### 注册账户
SIGNUP

If you don't already have a plotly account, either signup online or use the signup() function (see the help(signup) page for more details).

Note you can check if you have a username and API key with:
```r
plotly:::verify("username")
plotly:::verify("api_key")
```

### 认证
Find your credentials in our online settings. Set them in your R session with:
```r
Sys.setenv("plotly_username"="your_plotly_username")
Sys.setenv("plotly_api_key"="your_api_key")
```
### 例子
```r
library(plotly)
set.seed(100)
d <- diamonds[sample(nrow(diamonds), 1000), ]
plot_ly(d, x = carat, y = price, text = paste("Clarity: ", clarity),mode = "markers", color = carat, size = carat)
```

执行完成之后，会显示如下的内容
```
Success! Created a new plotly here -> https://plot.ly/~luojie2211/42
```

打开上面的链接，显示如下的内容：
+ plot
刚才绘制的图形
![](https://raw.githubusercontent.com/KillEdision/R-Notebook/master/plotly/Image%201.png)

+ data
绘制上面的图形所使用的数据
![](https://raw.githubusercontent.com/KillEdision/R-Notebook/master/plotly/Image%202.png)

+ code
绘制上面的图形的代码，可以在`R`、`Python`、`Json`、`JavaScript`、`Julia`等语言之间转换
![](https://raw.githubusercontent.com/KillEdision/R-Notebook/master/plotly/Image%203.png)  
![](https://raw.githubusercontent.com/KillEdision/R-Notebook/master/plotly/Image%204.png)

+ extras
作为上述图形的附件，当别人浏览该图形的时候，可以顺带下载该附件中的内容
![](https://raw.githubusercontent.com/KillEdision/R-Notebook/master/plotly/Image%205.png)

