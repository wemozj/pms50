
# python可视化50图解读(Pms50-Notes)
python可视化50图是由博主大佬Selva Prabhakaran于2018年12月在自己网站发布的一篇优秀的博文。当小编在学习数据可视化的时候发现了这篇优秀博文，但是
- 博文不是中文
- 代码没有注解
- 有的代码直接运行会报错
- 对可视化50图没有进行总结
- 等等

小编花了几个月的时间学习完这篇优秀的博文，认为优秀的博文应该让大多数人来一起学习，于是小编对于可视化50图每行代码进行注解，总结每篇博文背后非常重要的内容，等等

## 使用说明
此系列笔记解读涉及非常多的matplotlib、 seaborn等库的使用，没有太多涉及numpy、pandas库的使用。想要更多的学习数据分析内容，可以来参加Datawhale的数据分析组队学习。结合这些资料一起学习，相信你对数据分析有更加深刻的理解。
若你觉得此学习项目的同时有余力时，也可以学习李宏毅的系列课程，以及机器学习实战，sklearn等领域知识内容

李宏毅机器学习：https://github.com/datawhalechina/leeml-notes

李宏毅线性代数：https://github.com/datawhalechina/leela-notes

机器学习实战笔记(mlia-notes)+sklearn解读：https://github.com/datawhalechina/mlia-notes



## 笔记在线阅读

在线阅读地址：https://datawhalechina.github.io/pms50/

### 原博文地址链接
博文链接：https://www.machinelearningplus.com/plots/top-50-matplotlib-visualizations-the-master-plots-python/


# 目录
 - [P1 散点图](https://datawhalechina.github.io/pms50/#/chapter1/chapter1)
 - [P2 带边界的气泡图](https://datawhalechina.github.io/pms50/#/chapter2/chapter2)
 - [P3 带线性回归最佳拟合线的散点图 ](https://datawhalechina.github.io/pms50/#/chapter3/chapter3)
 - [P4 抖动图](https://datawhalechina.github.io/pms50/#/chapter4/chapter4)
 - [P5 计数图](https://datawhalechina.github.io/pms50/#/chapter5/chapter5)
 - [P6 边缘直方图](https://datawhalechina.github.io/pms50/#/chapter6/chapter6)
 - [P7 边缘箱形图](https://datawhalechina.github.io/pms50/#/chapter7/chapter7)
 - [P8 相关图](https://datawhalechina.github.io/pms50/#/chapter8/chapter8)
 - [P9 矩阵图](https://datawhalechina.github.io/pms50/#/chapter9/chapter9)
 - [P10 发散型条形图 ](https://datawhalechina.github.io/pms50/#/chapter10/chapter10)
 - [P11 发散型文本](https://datawhalechina.github.io/pms50/#/chapter11/chapter11)
 - [P12 发散型包点图](https://datawhalechina.github.io/pms50/#/chapter12/chapter12)
 - [P13 带标记的发散型棒棒糖图](https://datawhalechina.github.io/pms50/#/chapter13/chapter13)
 - [P14 面积图](https://datawhalechina.github.io/pms50/#/chapter14/chapter14)
 - [P15 有序条形图 ](https://datawhalechina.github.io/pms50/#/chapter15/chapter15)
 - [P16 棒棒糖图](https://datawhalechina.github.io/pms50/#/chapter16/chapter16)
 - [P17 包点图](https://datawhalechina.github.io/pms50/#/chapter17/chapter17)
 - [P18 坡度图](https://datawhalechina.github.io/pms50/#/chapter18/chapter18)
 - [P19 哑铃图](https://datawhalechina.github.io/pms50/#/chapter19/chapter19)
 - [P20 连续变量的直方图](https://datawhalechina.github.io/pms50/#/chapter20/chapter20) 
 - [P21 类型变量的直方图](https://datawhalechina.github.io/pms50/#/chapter21/chapter21)
 - [P22 密度图](https://datawhalechina.github.io/pms50/#/chapter22/chapter22)
 - [P23 直方密度线图](https://datawhalechina.github.io/pms50/#/chapter23/chapter23)
 - [P24 Joy Plot](https://datawhalechina.github.io/pms50/#/chapter24/chapter24)
 - [P25 分布式包点图](https://datawhalechina.github.io/pms50/#/chapter25/chapter25)
 - [P26 箱形图](https://datawhalechina.github.io/pms50/#/chapter26/chapter26)
 - [P27 包点+箱形图](https://datawhalechina.github.io/pms50/#/chapter27/chapter27)
 - [P28 小提琴图](https://datawhalechina.github.io/pms50/#/chapter28/chapter28)
 - [P29 人口金字塔](https://datawhalechina.github.io/pms50/#/chapter29/chapter29)
 - [P30 分类图](https://datawhalechina.github.io/pms50/#/chapter30/chapter30)
 - [P31 华夫饼图](https://datawhalechina.github.io/pms50/#/chapter31/chapter31)
 - [P32 饼图](https://datawhalechina.github.io/pms50/#/chapter32/chapter32)
 - [P33 树形图](https://datawhalechina.github.io/pms50/#/chapter33/chapter33)
 - [P34 条形图 ](https://datawhalechina.github.io/pms50/#/chapter34/chapter34)
 - [P35 时间序列图](https://datawhalechina.github.io/pms50/#/chapter35/chapter35)
 - [P36 带波峰波谷标记的时序图](https://datawhalechina.github.io/pms50/#/chapter36/chapter36)
 - [P37 自相关和部分自相关图](https://datawhalechina.github.io/pms50/#/chapter37/chapter37)
 - [P38 交叉相关图 ](https://datawhalechina.github.io/pms50/#/chapter38/chapter38)
 - [P39 时间序列分解图](https://datawhalechina.github.io/pms50/#/chapter39/chapter39)
 - [P40 多个时间序列](https://datawhalechina.github.io/pms50/#/chapter40/chapter40) 
 - [P41 使用辅助 Y 轴来绘制不同范围的图形](https://datawhalechina.github.io/pms50/#/chapter41/chapter41)
 - [P42 带有误差带的时间序列](https://datawhalechina.github.io/pms50/#/chapter42/chapter42)
 - [P43 堆积面积图](https://datawhalechina.github.io/pms50/#/chapter43/chapter43)
 - [P44 未堆积的面积图 ](https://datawhalechina.github.io/pms50/#/chapter44/chapter44)
 - [P45 日历热力图](https://datawhalechina.github.io/pms50/#/chapter45/chapter45)
 - [P46 季节图](https://datawhalechina.github.io/pms50/#/chapter46/chapter46)
 - [P47 树状图](https://datawhalechina.github.io/pms50/#/chapter47/chapter47)
 - [P48 簇状图](https://datawhalechina.github.io/pms50/#/chapter48/chapter48)
 - [P49 安德鲁斯曲线](https://datawhalechina.github.io/pms50/#/chapter49/chapter49)
 - [P50 平行坐标](https://datawhalechina.github.io/pms50/#/chapter50/chapter50)


















