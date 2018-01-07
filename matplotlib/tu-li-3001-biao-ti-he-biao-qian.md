这里介绍如何设置坐标，坐标标题和标签

```
import matplotlib.pyplot as plt

x = [1,2]
y = [5,7]

x2 = [1,2]
y2 = [3,9]

plt.plot(x, y, label='First Line')
plt.plot(x2, y2, label='Second Line')

plt.xlabel('Plot Number')
plt.ylabel('Important var')
plt.title('Interesting Graph\nCheck it out')
plt.legend()
plt.show()
```



