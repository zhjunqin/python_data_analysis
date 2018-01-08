gif动画

```
# -*- coding: utf-8 -*-

import sys
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

fig, ax = plt.subplots()


# 画点和线
x = np.arange(0, 20, 1)
ax.scatter(x, x + np.random.normal(0, 3.0, len(x)))
line, = ax.plot(x, x - 5, 'r-', linewidth=2)

def init():  #初始化函数，可以在这里画一些初始化的数据
    return line, ax # 必须返回一个可以迭代的对象，如果只返回一个也就是 return line,

def update(i): # 每次动画调用的函数
    label = 'timestep {0}'.format(i)
    # 更新直线和X轴标签
    line.set_ydata(x - 5 + i) #每次调整直线
    ax.set_xlabel(label)
    return line, ax  # 同上，返回可迭代对象

# FuncAnimation每帧都会调用update; 这里是5帧，每帧间隔1s
anim = FuncAnimation(fig, update, init_func=init, frames=np.arange(0, 5), interval=1000)
anim.save('line.gif', dpi=80, writer='imagemagick')
plt.show()
```

![](/assets/pla_figure_4.gif)

API：[https://matplotlib.org/devdocs/api/\_as\_gen/matplotlib.animation.FuncAnimation.html\#matplotlib.animation.FuncAnimation](https://matplotlib.org/devdocs/api/_as_gen/matplotlib.animation.FuncAnimation.html#matplotlib.animation.FuncAnimation)

```
class matplotlib.animation.FuncAnimation(fig, func, frames=None, init_func=None, fargs=None, save_count=None, **kwargs)

Makes an animation by repeatedly calling a function func.
```



