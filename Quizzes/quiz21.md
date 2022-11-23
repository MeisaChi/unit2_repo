```.py
def get_truth() ->str:
    A = False
    B = False
    C = False
    D = False
    out = ""
    print("|  A  |  B  |  C  | AB + not B + not CB |")
    for i in range(8):
        C = not C
        if (i+1)%2 == 0:
            B = not B
        if (i+1)%4 == 0:
            A = not A
        if int(A and B) or int(not B) or int(not B and C) == 1:
            D = True
        print("| ", int(A), " | ", int(B), " | ", int(C), " |         ", int(D), "         |")
        D = False
    return out
table = get_truth()
print(table)

```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz21.png)
