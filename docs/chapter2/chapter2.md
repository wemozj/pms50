> > ++++## 关联 （Correlation）

关联图表用于可视化2个或更多变量之间的关系。 也就是说，一个变量如何相对于另一个变化。


### 带边界的气泡图

有时，您希望在边界内显示一组点以强调其重要性。 在这个例子中，你从数据框中获取记录，并用下面代码中描述的 encircle（） 来使边界显示出来。


#### 导入所需要的库


```
# 导入numpy库
import numpy as np
# 导入pandas库
import pandas as pd
# 导入matplotlib库
import matplotlib as mpl
import matplotlib.pyplot as plt
# 导入seaborn库
import seaborn as sns
# 在jupyter notebook显示图像
%matplotlib inline

# 导入patches
from matplotlib import patches
# 导入ConvexHull
from scipy.spatial import ConvexHull
```

#### 设定图像各种属性


```
large = 22; med = 16; small = 12
            # 设置子图上的标题字体
params = {'axes.titlesize': large,  
            # 设置图例的字体
          'legend.fontsize': med,
            # 设置图像的画布
          'figure.figsize': (16, 10),  
            # 设置标签的字体
          'axes.labelsize': med, 
            # 设置x轴上的标尺的字体
          'xtick.labelsize': med,  
            # 设置整个画布的标题字体
          'ytick.labelsize': med,  
          'figure.titlesize': large}  
# 更新默认属性
plt.rcParams.update(params)  
 # 设定整体风格
plt.style.use('seaborn-whitegrid')
# 设定整体背景风格
sns.set_style("white")  
```

#### 测试版本

```
print(mpl.__version__)
print(sns.__version__)
```
3.1.0

0.9.0


#### 程序代码


```
# step1:导入数据
midwest = pd.read_csv("https://raw.githubusercontent.com/selva86/datasets/master/midwest_filter.csv")
# 准备数据以及颜色
    # 使用np.umique对midwest["category"]去重
categories = np.unique(midwest["category"])
    # 使用列表推导式，建立colors列表
    # 14个数据，0-13
colors = [plt.cm.tab10(i/float(len(categories) - 1)) for i in range(len(categories))]

# step2:为每个类别绘制具有独特颜色的散点图
    # 建立画布
plt.figure(figsize=(16, 10),  # 绘图尺寸默认为（6.4, 4.8）
           dpi = 80,          # 图像分辨效率，默认dpi为100
          facecolor =  "w",   # 背景颜色，默认为白色
          edgecolor = 'k')    # 边框颜色，默认为白色

    
 
    # 绘图
         # 使用函数enumerate：将可遍历的数据对象组合为一个索引序列，同时列出数据和数据索引
for i, category in enumerate(categories):
    plt.scatter('area', 'poptotal',  # 横纵坐标
                data=midwest.loc[midwest.category==category, :]    # 横纵坐标所对应的数据 
                , s="dot_size" # 数据尺寸大小 
                , c= np.array(colors[i]).reshape(1,-1)
                , label=str(category)  # 设定标签名称
                , edgecolors= np.array(colors[i]).reshape(1,-1)   # 标记的边缘颜色
                # , alpha = 0.7
                , linewidths=.5) 

# step3:Encircling
    
    # 定义绘制画环绕的函数
def encircle(x, y, ax=None, **kw):
        # 如果没有子图对象，那么就创建一个新的子图对象
    if not ax: ax = plt.gca()
        # p.c_中的c是column（列）的缩写，是按列叠加两个矩阵的意思，也可以说是按行连接两个矩阵，就是把两矩阵左右相加，要求行数相等，类似于pandas中的merge()。
    p = np.c_[x, y]
        # 将数据集输入到ConverHull中，自动生成凸包类型的对象(hull)
    hull = ConvexHull(p)
        # 利用plt.Polygon绘制多边形
    ploy = plt.Polygon(p[hull.vertices, :], **kw)
        # 将多边形ploy修补到当前子图中
    ax.add_patch(ploy)
    
    # 选择要包围的数据
midwest_encircle_data = midwest.loc[midwest.state == 'IN', :]

# step4:绘制顶点周围的多边形
    # 绘画线条
encircle(midwest_encircle_data.area,
         midwest_encircle_data.poptotal,
        ec = "firebrick",   # 线条颜色
        fc = 'none',
        linewidth = 1.5)
    # 背景颜色
encircle(midwest_encircle_data.area, 
        midwest_encircle_data.poptotal,
        ec = 'none',
        fc = 'gold',
        alpha = 0.1)

# step5:装饰
    # 设置x坐标轴的范围
plt.gca().set(xlim = (0.0, 0.12),    
    # 设置y坐标轴的范围          
              ylim = (0, 90000),
    # 设置x坐标的标题
             xlabel = "Area",  
    # 设置y坐标的标题
             ylabel = "Population")  
    # 设置x坐标的字体
plt.xticks(fontsize = 12)
    # 设置y坐标的字体
plt.yticks(fontsize = 12)
    # 设置图像标题和字体字体
plt.title("Bubble Plot with Encircling", fontsize=22)
    # 显示图例，设置图例大小
plt.legend(fontsize = 12)
plt.show()
```
### 带边界的气泡图
![chapter1-0.png](res/chapter2-1.png)













