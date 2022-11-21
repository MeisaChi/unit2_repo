## Part A
```.py
from matplotlib import pyplot as plt
x = []
y = []
st = -10
for i in range(-10,10):
    x.append(st)
    st += 0.2
    y.append(2 * (i + 5) ** 2)
plt.plot(x, y, color="red")
plt.show()
```

![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz24.png)
## Part B
