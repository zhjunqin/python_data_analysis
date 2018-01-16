Numpy中的axis概念

> Source:
>
> http://changtw-blog.logdown.com/posts/895468-python-numpy-axis-concept-organize-notes

以一個3x3 numpy array为例

```
ndarray = numpy.arange(1,10).reshape(3,3)

[[1, 2, 3], 
[4, 5, 6], 
[7, 8, 9]]
```

![](/assets/axis_1.jpg)

![](/assets/axis_2.jpg)

`ndarray[0]`表示取軸0的第0項,也就是`ndarray[0][:]`取軸0第一項然後對應的軸1每項都要

![](/assets/axis_3.jpg)

`ndarray[0][1]`表示先選取軸0的第0項,接著再對應取軸1的第1項

![](/assets/axis_4.jpg)

`ndarray[:][0:2]` 表示軸0的項目全部都要,但只取每一項的軸1的0到1項

![](/assets/axis_5.jpg)

```
ndarray.sum(axis = 1) -> array([ 6, 15, 24])
```

表示將軸1的各項相加,但不將軸0合併\(合併了軸0就等於一般ndarray.sum\(\)的結果了\),也就是軸0的各項分別各自將其軸1各項相加\(每列各自將其對應軸0各項相加\)

![](/assets/axis_6.jpg)

> Source:
>
> http://blog.csdn.net/fangjian1204/article/details/53055219

通过不同的axis，numpy会沿着不同的方向进行操作：

如果不设置，那么对所有的元素操作；如果axis=0，则沿着纵轴进行操作；axis=1，则沿着横轴进行操作。但这只是简单的二位数组，如果是多维的呢？可以总结为一句话：设axis=i，则numpy沿着第i个下标变化的放下进行操作。

