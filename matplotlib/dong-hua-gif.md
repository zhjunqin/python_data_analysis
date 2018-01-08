

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

def init():
    return line, ax

def update(i):
    label = 'timestep {0}'.format(i)
    # 更新直线和X轴标签
    line.set_ydata(x - 5 + i)
    ax.set_xlabel(label)
    return line, ax
 
# FuncAnimation每帧都会调用update; 这里是5帧，每帧间隔1s
anim = FuncAnimation(fig, update, init_func=init, frames=np.arange(0, 5), interval=1000)
anim.save('line.gif', dpi=80, writer='imagemagick')
plt.show()
```



