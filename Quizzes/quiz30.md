## Part A
```.py
import matplotlib.pyplot as plt

x = []
h = [57.0, 56.0, 57.0, 56.0, 55.0, 55.0, 54.0, 54.0, 54.0, 53.0, 53.0, 54.0, 53.0, 53.0, 52.0, 52.0, 51.0, 51.0, 51.0, 50.0, 50.0, 49.0, 50.0, 49.0, 49.0, 48.0, 49.0, 49.0, 48.0, 48.0, 48.0, 49.0]

ev4 = 4
h_mean = []
for i in range(0,len(h),ev4):
    data = h[i:i+ev4]
    h_mean.append(sum(data)/ev4)
for i in range(0, len(h_mean)):
    x.append(i)

plt.plot(x, h_mean, color="red")
plt.xlabel("Samples")
plt.ylabel("Relative Humidity")
plt.show()
```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz30.png)
## Part B
