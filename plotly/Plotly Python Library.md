# GETTING STARTED
## Getting Started: Plotly for Python
### 安装
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

### 初始化
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

### Start plotting!
#### Fire up Python!
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

### Credentials
The initialization step places a special .plotly/.credentials file in your home directory. Your ~/.plotly/.credentials file should look something like this:
```json
{
    "username": "DemoAccount",
    "stream_ids": ["ylosqsyet5", "h2ct8btk1s", "oxz4fm883b"],
    "api_key": "lr1c37zw81"
}
```
You can change the contents of this file manually or as described in the Initialization section.

## Plotly for IPython Notebooks

Instructions on how to install Plotly's Python package can be found on the PLOTLY FOR PYTHON GETTING STARTED PAGE.

### Creating an interactive graph inside IPython notebook
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

### Converting a matplotlib graph into an interactive graph inside an IPython notebook
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
### Embedding a Plotly graph inside an IPython notebook
```python
import plotly.tools as tls

tls.embed("https://plot.ly/~streaming-demos/4")
```

## User Guide
### Why a User Guide? 
The User Guide project has the goal of giving Plotly's Python/IPython users extensive documentation on all of Plotly's features.

Whereas Plotly's web [documentation](https://plot.ly/python/) is meant to serve Plotly beginners just looking to make a simple plot and experienced users trying out a new plot type, the User Guide intends to turn beginner and intermediate Plotly users into experts.

It is assumed that readers of the User Guide are comfortable with Python terminology (e.g. know what Python objects, lists, dictionaries and functions are). But, there is absolutely no need to be a Python guru to follow the User Guide's content.


### Table of Contents: 
The User Guide is entirely written inside [IPython notebooks](http://ipython.org/notebook.html) . An IPython notebook is a web-based interactive computational environment where code excution, test, mathematics, plots and rich media can be combined into a single document. Big thanks to [Cam Davidson-Pilon](http://nbviewer.ipython.org/github/CamDavidsonPilon/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers/blob/master/Prologue/Prologue.ipynb) and [Lorena A. Barba](http://lorenabarba.com/blog/announcing-aeropython/#.U1ULXdX1LJ4.google_plusone_share) for notebook styling ideas.

The User Guide's Github [repository](https://github.com/plotly/python-user-guide) is divided into folders, one for each section or appendix. Each folder contains one or several IPython notebooks and the required data files to run them. You are currently reading the User Guide's homepage.

Each section is intended to be a single lecture . While the content is mostly divided by plot types, each lecture contains valuable examples of Plotly's customization flexibility as well as templates that users can incorporate into their own work.

## CURRENT SECTIONS:
+ [Section 0](https://plot.ly/python/overview/): Getting Started with Plotly
+ [Section 1](https://plot.ly/python/line-and-scatter-plots-tutorial/): Line and Scatter Plots
+ [Section 2](https://plot.ly/python/bar-charts-tutorial): Bar Charts
+ [Section 3](https://plot.ly/python/bubble-charts-tutorial): Bubble Charts
+ [Section 4](https://plot.ly/python/histograms-and-box-plots-tutorial): Histograms and Box Plots
+ [Section 5](https://plot.ly/python/heatmaps-contours-and-2dhistograms-tutorial): Heatmaps, Contours and 2D Histograms
+ [Section 6](https://plot.ly/python/matplotlib-to-plotly-tutorial): Convert your Matplotlib plots to Plotly
+ [Section 7](https://plot.ly/python/streaming-tutorial): Plotly's Streaming API
+ [Section 8](https://plot.ly/python/3d-plots-tutorial): 3D Plots
+ [Appendix A](https://plot.ly/python/python-tutorial): Python Basics

### PROPOSED FUTURE SECTIONS:
+ Sections ?: Polar Charts, Maps, ...
+ Appendices ?: Command Line, pip, IPython Primer, Useful templates, FAQ, ...
+ Suggestions?

### Installation guidelines 
#### Step 1
The User Guide assumes:
+ The lastest version of Plotly's Python package (see step 3 )
+ Python version 2.7.5+ or 2.7.6 with
  + numpy (version 1.8.1), for all sections
  + pandas (version 0.13.1), for sections 3, 5 and 7.3
  + scipy (version 0.13.3), for section 4 and 7
  + matplotlib (version 1.3.1), for section 6
+ IPython version 2.1.0


#### Step 2 
Install Plotly's Python package.
To do so, use the package manager pip inside a terminal or command prompt:
+ $ pip install plotly

On Mac OS or Linux machines, enter:
+ $ sudo pip install plotly ,  for a system-wide install
or 
+ $ pip install --user plotly ,  for user-only use
If you do not have pip installed on your machine, follow pip's [installation guidelines](https://pip.pypa.io/en/latest/installing.html) .

#### Step 3 
If you already have Plotly's Python package installed, check its version, inside Python or IPython, with:
```python
import plotly
plotly.__version__
```

If not latest version (as displayed above), upgrade by running, inside a terminal/command prompt:
+ $ pip install plotly --upgrade
+ or $ sudo pip install --upgrade
+ or $ pip install --user plotly --upgrade

#### Step 4 
If you don't already have an account, sign up for Plotly:
+ Go to [plot.ly](https://plot.ly/) and click on the Sign up button. 
![](https://plot.ly/gh-pages/documentation/static//images/py-user-guide-img/image02.png)  
After signing up, we will receive a verification email from accounts@plot.ly allowing you to receive notifications and reset your password if desired.

#### Step 5 
Get your username and API key:
+ After signing in, click on the drop-down menu at the top-right corner of the page and then on the settings link
![](https://plot.ly/gh-pages/documentation/static//images/py-user-guide-img/image03.png)  

+ Your API key and username are listed under API settings .
![](https://plot.ly/gh-pages/documentation/static//images/py-user-guide-img/image04.png)

### Step 6 
Although not required, we recommend setting up a credentials file on your machine:
In Python or IPython,
```python
import plotly.tools as tls
tls.set_credentials_file(username="your_username",api_key="your_api_key")
```
Where the username and api_key keyword arguments are filled in with your own as found in step 5 .

This creates a .credentials file in a folder called $HOME/.plotly/ (where $HOME is your home directory) storing your username and API key locally in JSON file.

Moreover, inside Python or IPython, with:
```python
credentials = tls.get_credentials_file()
```
writes your Plotly credentials into a Python dictionary and assigns it to a variable.

#### Step 7 ¶
Import the Plotly modules and sign in to Plotly from Python or IPython.  
In version 1.0 and up of Plotly's Python API, this requires only one line of code once your credentials file is set up:
```python
# (*) Tools to communicate with Plotly's server
import plotly.plotly as py
```
And there you go. You are now ready to make plots using Plotly and its Python API.
While being imported, the plotly.plotly module looks for your credentials file on your machine and automatically uses it to sign in to Plotly's servers.  
Using credentials files allows users to share code without having to type in (let alone remember) their own username and API key every time they want to generate a new Plotly plot or modify an existing Plotly plot.  
That said, if more convenient, users can still manually sign in to Plotly by typing:
```python
py.sign_in('your_username','your_api_key')
```

To make the most out of the Plotly Python experience, you will end up using two other Plotly submodules. These are:
```python
 # (*) Useful Python/Plotly tools 
import plotly.tools as tls

# (*) Graph object to piece together your Plotly plots
from plotly.graph_objs import Figure, Data, Layout
```

Where their respective features are covered in full details in the User Guide.


