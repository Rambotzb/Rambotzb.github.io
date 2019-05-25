# Matplotlib 数据可视化
## Matplotlib基本使用
### 基本用法
matplotlib库里面最常用的就是pyplot,并且使用pyplot时经常使用numpy来处理数据。这里给出一段画出一条直线的代码：
~~~python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(-1, 1, 50)  #在(-1，1)之间生成50个点
y = 2*x + 1

plt.figure()  #使用figure()函数来定义一个图像窗口
plt.plot(x, y)  #使用plot()来绘制函数图像
plt.show()  #使用show()来显示图像，一般在设置好图像后最后使用
~~~
<img src="https://morvanzhou.github.io/static/results/plt/2_1.png" width=50%>
### figure图像
在figure产生的窗口中，并不仅仅能存在一条图线。
~~~python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(-3, 3, 50)
y1 = 2*x +1
y2 = x**2  #x的平方

plt.figure(num=3, figsize=(8, 5))  #编号为3，大小为(8,5)的图像窗口
plt.plot(x, y2)
plt.plot(x, y1, color='red', linewidth=1.0, linestyle='--')
plot.show()
~~~

### 设置坐标轴
以下代码能够实现对坐标轴的自定义设置
~~~python
#对坐标轴的范围进行更改
plt.xlim((-1,2))
plt.ylim((-2,3))

#对坐标轴的标签进行修改
plt.xlabel('I am x')
plt.ylabel('I am y')

#对坐标轴刻度进行修改
new_ticks = np.linspace(-1, 2, 5)
plt.xticks(new_ticks)
plt.yticks([-2, -1.8,-1, 1.22, 3],[r'$really\ bad$', r'$bad$', r'$normal$', r'$good$', r'$really\ good$']])

#设置坐标轴样式
ax = plt.gca()  #获取当前坐标轴信息
ax.spines['right'].set_color('none')  #将
ax.spines['top'].set_color('none')
~~~
<img src="https://morvanzhou.github.io/static/results/plt/2_4_1.png">
