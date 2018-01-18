```
# -*- coding: utf-8 -*-

import numpy as np
import matplotlib.pyplot as plt
import matplotlib.patches as patches

fig = plt.figure() 
axes = fig.add_subplot(111) 

# 菱形
axes.plot([-1, 0], [0, 1], color='r', label='p=1', linewidth=1)
axes.plot([-1, 0], [0, -1], color='r', linewidth=1)
axes.plot([0, 1], [1, 0], color='r',  linewidth=1)
axes.plot([0, 1], [-1, 0], color='r',  linewidth=1)

# 圆的基本信息
# 1.圆半径
r = 1.0
# 2.圆心坐标
a, b = (0., 0.)
theta = np.arange(0, 2*np.pi, 0.01)
x = a + r * np.cos(theta)
y = b + r * np.sin(theta)
axes.plot(x, y, color='blue', label='p=2', linewidth=1)

# 矩形/正方形
axes.add_patch(
    patches.Rectangle(
        (-1, -1),
        2,
        2,
        fill=False,
        edgecolor="green",
        linewidth=1,
        label=r'$ p=\infty $'
    )
)

axes.axis('equal')

axes.spines['left'].set_position('center')
axes.spines['right'].set_color('none')
axes.spines['bottom'].set_position('center')
axes.spines['top'].set_color('none')
axes.spines['left'].set_smart_bounds(True)
axes.spines['bottom'].set_smart_bounds(True)
axes.xaxis.set_ticks_position('bottom')
axes.set_xticks([-1,0,1])  
axes.yaxis.set_ticks_position('left')
axes.set_yticks([-1,1])  

plt.title('Lp distance = 1')
plt.legend(bbox_to_anchor=(1.05, 1), loc=1, borderaxespad=0.)
plt.show()
```



