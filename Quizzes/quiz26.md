## Part A
```.py
import matplotlib.pyplot as plt
import numpy as np

x = []
h = [57.0, 56.0, 57.0, 56.0, 55.0, 55.0, 54.0, 54.0, 54.0, 53.0, 53.0, 54.0, 53.0, 53.0, 52.0, 52.0, 51.0, 51.0, 51.0, 50.0, 50.0, 49.0, 50.0, 49.0, 49.0, 48.0, 49.0, 49.0, 48.0, 48.0, 48.0, 49.0]
for i in range(1, 33):
    x.append(i)

m, b = np.polyfit(x, h, 1)
print(f"Linear equasion is y={m:.2f}x+({b:.2f})")
x_model = [1, 32]
h_model = []
for i in x_model:
    h_model.append(m * i + b)

plt.plot(x_model, h_model, color="pink")
plt.text(20, 54, f"y={m:.2f}x+({b:.2f})", color="blue")
plt.xlabel("Samples")
plt.ylabel("Relative Humidity %")
plt.scatter(x, h, color="red")
plt.show()
```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz26.png)
## Part B
#### Hex = #e6e627
#### Red = 230, Green = 230, Blue = 39
