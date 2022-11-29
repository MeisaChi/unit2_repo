## Part A
```.py
import matplotlib.pyplot as plt
plt.style.use("seaborn-v0_8-darkgrid")
import numpy as np

x = []
sensorA = [16, 24, 24, 9, 23, 26, 26, 23, 25, 14]
sensorB = [2, 19, 25, 10, 11, 24, 17, 7, 24, 17]
sensorC = [15, 11, 24, 21, 6, 2, 18, 27, 1, 16]
for a in range(len(sensorA)):
    x.append(+a)

mean = []
standard_dev = []
for s in range(len(sensorA)):
    data = [sensorA[s], sensorB[s], sensorC[s]]
    mean.append(np.mean(data))
    standard_dev.append(np.std(data))
plt.errorbar(x, mean, standard_dev, fmt="o", color="#87677B")

plt.show()
```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz27.png)
## Part B
#### Red = 250
#### Green = 100
#### Bule = 10
#### Hex = 
