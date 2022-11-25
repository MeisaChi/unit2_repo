## Part A
```.py
def get_truth() ->str:
    A = False
    B = False
    C = False
    out = ""
    print("|  A  |  B  |  C  |")
    for i in range(0,8):
        print("| ",int(A)," | ",int(B)," | ",int(C)," |")
        C = not C
        if (i+1)%2 == 0:
            B = not B
        if (i+1)%4 == 0:
            A = not A
    return out
table = get_truth()
print(table)
```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz20.png)
## Flow Diagram
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/20.jpg)
## Part B
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/20b.jpg)
