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

