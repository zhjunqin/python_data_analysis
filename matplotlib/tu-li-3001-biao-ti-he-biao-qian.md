这里介绍如何设置坐标，坐标标题和标签

```
import matplotlib.pyplot as plt

x = [1,2]
y = [5,7]

x2 = [1,2]
y2 = [3,9]

plt.plot(x, y, label='First Line')    # 画直线，打标签
plt.plot(x2, y2, label='Second Line')

plt.xlabel('Plot Number')        # X轴标签
plt.ylabel('Important var')      # Y轴标签
plt.title('Interesting Graph\nCheck it out')  # 图的描述
plt.legend()                 # 画出带"label"的
plt.show()
```

![](/assets/Figure_1.png)

