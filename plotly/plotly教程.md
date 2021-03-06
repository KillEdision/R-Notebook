# [Plotly for R](https://plot.ly/r/getting-started/)
## 安装
plotly is not (yet) available on CRAN, but you can install it via devtools:
```r
install.packages("viridis") # dependency
install.packages("devtools")
devtools::install_github("ropensci/plotly")
```
### 注册账户
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

## 其他的代码
### KNOW AND LOVE GGPLOT2? TRY GGPLOTLY
```r
p <- ggplot(data = d, aes(x = carat, y = price)) +
  geom_point(aes(text = paste("Clarity:", clarity)), size = 4) +
  geom_smooth(aes(colour = cut, fill = cut)) + facet_wrap(~ cut)

(gg <- ggplotly(p))
```
### MIX DATA MANIPULATION AND VISUALIZATION VERBS
```r
str(p <- plot_ly(economics, x = date, y = uempmed))
p %>%
  add_trace(y = fitted(loess(uempmed ~ as.numeric(date)))) %>%
  layout(title = "Median duration of unemployment (in weeks)",
         showlegend = FALSE) %>%
  dplyr::filter(uempmed == max(uempmed)) %>%
  layout(annotations = list(x = date, y = uempmed, text = "Peak", showarrow = T))
```

### 3D WEBGL AND MORE
```r
plot_ly(z = volcano, type = "surface")
```

# Plotly for Python
## 安装
To install Plotly's Python package, use the package manager pip inside your terminal.
```python
$ pip install plotly
```
or
```python
$ sudo pip install plotly
```
If you don't have pip installed on your machine, click here for pip's installation instructions.
Plotly's Python package is updated frequently! To upgrade, run:
```python
$ pip install plotly --upgrade
```

## 初始化
In the terminal, copy and paste the following to install the Plotly library and set your user credentials.
```python
$ pip install plotly
$ python -c "import plotly; plotly.tools.set_credentials_file(username='DemoAccount', api_key='lr1c37zw81')"
```

You'll need to replace 'DemoAccount' and 'lr1c37zw81' with your Plotly username and API key.
Find my API key.

### Special Instructions for Plotly On-Premise users
Your API key for account on the public cloud will be different than the API key in Plotly On-Premise. Visit https://plotly.your-company.com/settings/api/ to find your Plotly On-Premise API key. Remember to replace "your-company.com" with the URL of your Plotly On-Premise server.  
If your company has a Plotly On-Premise server, change the Python API endpoint so that it points to your company's Plotly server instead of Plotly's cloud.  

In your Terminal, enter:
```python
$ python -c "import plotly; plotly.tools.set_config_file(plotly_domain='https://plotly.your-company.com',
plotly_streaming_domain='stream-plotly.your-company.com', plotly_api_domain='https://api-plotly.your-company.com')"
```

## Start plotting!
### Fire up Python!
```python
$ python
```

```python
import plotly.plotly as py
from plotly.graph_objs import Scatter

trace0 = Scatter(x=[1, 2, 3, 4],
    y=[10, 15, 13, 17]
)
trace1 = Scatter(
    x=[1, 2, 3, 4],
    y=[16, 5, 11, 9]
)
data = [trace0, trace1]

unique_url = py.plot(data, filename = 'basic-line')
```

程序执行到这一步，会自动打开网页，内容如下：

+ plot
![](https://raw.githubusercontent.com/KillEdision/R-Notebook/master/plotly/Image%206.png)

+ data
![](https://raw.githubusercontent.com/KillEdision/R-Notebook/master/plotly/Image%207.png)

+ code
![](https://raw.githubusercontent.com/KillEdision/R-Notebook/master/plotly/Image%208.png)

You can also create plotly graphs with matplotlib syntax. Learn more in our [matplotlib documentation](https://plot.ly/matplotlib/).

You can also create plotly graphs within an IPython notebook. Learn more in our [IPython notebook documentation](https://plot.ly/ipython-notebooks/).

By default, plotly graphs are public and saved to [your online plotly account](https://plot.ly/organize). To create graphs offline and locally, [license plotly offline](https://plot.ly/python/offline). To create private graphs, set sharing to 'private':
```python
py.plot(data, share='private', filename='private-plot') # you'll need to be logged in to plotly to view this graph
```
or, create a randomized "secret" URL:
```python
py.plot(data, share='secret', filename='secret-plot') # anybody with the URL can view the plot
```
[Learn more about private charting](https://plot.ly/python/privacy/).

## Credentials
The initialization step places a special .plotly/.credentials file in your home directory. Your ~/.plotly/.credentials file should look something like this:
```json
{
    "username": "DemoAccount",
    "stream_ids": ["ylosqsyet5", "h2ct8btk1s", "oxz4fm883b"],
    "api_key": "lr1c37zw81"
}
```
You can change the contents of this file manually or as described in the Initialization section.

# Plotly for IPython Notebooks

Instructions on how to install Plotly's Python package can be found on the PLOTLY FOR PYTHON GETTING STARTED PAGE.

## Creating an interactive graph inside IPython notebook
```python
import plotly.plotly as py
from plotly.graph_objs import *

trace0 = Scatter(
  x=[1, 2, 3, 4],
  y=[10, 15, 13, 17]
)
trace1 = Scatter(
  x=[1, 2, 3, 4],
  y=[16, 5, 11, 9]
)
data = Data([trace0, trace1])

py.iplot(data, filename = 'basic-line')
```

## Converting a matplotlib graph into an interactive graph inside an IPython notebook
```python
import matplotlib.pyplot as plt
import numpy as np
import plotly.plotly as py

n = 50
x, y, z, s, ew = np.random.rand(5, n)
c, ec = np.random.rand(2, n, 4)
area_scale, width_scale = 500, 5

fig, ax = plt.subplots()
sc = ax.scatter(x, y, c=c,
                s=np.square(s)*area_scale,
                edgecolor=ec,
                linewidth=ew*width_scale)
ax.grid()

py.iplot_mpl(fig)
```
Embedding a Plotly graph inside an IPython notebook
```python
import plotly.tools as tls

tls.embed("https://plot.ly/~streaming-demos/4")
```