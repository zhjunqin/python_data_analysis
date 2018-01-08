直线

```
import matplotlib.pyplot as plt
import numpy as np

x1 = [1,3,5,7]
y1 = [3,4,1,2]
x2 = np.array([1,2,3,4])
def fun(x):
    return 2*x + 3

plt.plot(x1,y1, label='positive', color='g',  marker="o")
plt.plot(x2,fun(x2), label='negative', color='r', marker="x")

plt.xlabel('x')
plt.ylabel('y')
plt.title('Interesting Graph\nCheck it out')
plt.legend()
plt.show()
```

![](/assets/pla_figure_3.png)



API文档：https://matplotlib.org/devdocs/api/\_as\_gen/matplotlib.pyplot.plot.html\#matplotlib.pyplot.plot





