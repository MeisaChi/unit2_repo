## Part A
```.py
import random
random.seed(1234)
def produce (n, m, s)->str:
    print(f"|{'x'.center(10)}|{'y'.center(10)}|")
    x_out = []
    y_out = []
    for i in range(0,n):
        x = random.randint(0,100)
        x_out.append(x)
        y = x**(1/2*((m/s)**2))
        y_out.append(y)
        y_str = f"{y:.2f}"
        print(f"|{str(x).center(10)}|{y_str.center(10)}|")
    return y_out, x_out

from matplotlib import pyplot as plt

my_y, my_x = produce(n=10, m=3, s=2)
plt.plot(my_x, my_y, color="red", marker="*")
plt.xlabel("Variable x")
plt.ylabel("$y=x^{1/2(m/s)^2}$")
plt.show()
```

![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz23.png)
## Part B
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/23b.jpg)
