```.py
import matplotlib.pyplot as plt
import numpy as np

x = [1, 2, 3, 1.5, 4, 2.5, 6, 4, 3, 5.5, 5, 2]
y = [3, 4, 8, 4.5, 10, 5, 15, 9, 5, 16, 13, 3]

m, b = np.polyfit(x, y, 1)
print(f"Linear equasion is y={m:.2f}x+({b:.2f})")
x_model = [1, 6]
y_model = []
for i in x_model:
    y_model.append(m * i + b)

plt.scatter(x, y, color="mediumpurple")
plt.xlabel("x")
plt.ylabel("y")
plt.plot(x_model, y_model, color="pink")

#prediction of y when x=7
x_7 = 7
y_pred_7 = m * x_7 + b
print(f"The prediction for x=7 is {y_pred_7:.3}")
plt.plot(x_7, y_pred_7, "b*", markersize = 12)
plt.text(6.2, 17, f"y(7)={y_pred_7:.3}", color="blue")

x_3p5 = 3.5
y_pred_3p5 = m * x_3p5 + b
print(f"The prediction for x=3.5 is {y_pred_3p5:.3}")
plt.plot(x_3p5, y_pred_3p5, "b*", markersize = 12)
plt.text(3, 7, f"y(3.5)={y_pred_3p5:.3}", color="blue")

plt.show()
```
