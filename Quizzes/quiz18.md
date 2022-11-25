```.py
def numberMatches(m,cms)->int:
    out = 0
    if (m*100)/cms%5 > 0:
        out += 1
    else:
        pass
    out += (m * 100) / cms / 5
    return int(out)

out1=numberMatches(100,100)
print(out1)
out2=numberMatches(250,110)
print(out2)
out3=numberMatches(500,150)
print(out3)
out4=numberMatches(12345,123)
print(out4)
```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz18.png)
## Flow diagram
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/18.jpg)
