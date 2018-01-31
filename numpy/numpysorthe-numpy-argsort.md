> Source:[https://stackoverflow.com/questions/19804091/sort-using-argsort-in-python](https://stackoverflow.com/questions/19804091/sort-using-argsort-in-python)

np.argsort是返回一个数组，里面的值是数组的下标，下标对应着排好序的数组

np.sort是返回一个数组，该数组就是将原数组排序好的结果

```
>>> arr = [5,3,7,2,6,34,46,344,545,32,5,22]
>>> np.sort(arr)
array([  2,   3,   5,   5,   6,   7,  22,  32,  34,  46, 344, 545])
>>> np.argsort(arr)
array([ 3,  1,  0, 10,  4,  2, 11,  9,  5,  6,  7,  8])
>>> arr
[5, 3, 7, 2, 6, 34, 46, 344, 545, 32, 5, 22]
```



