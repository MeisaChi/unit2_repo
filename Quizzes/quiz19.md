## Part A
```.py
def get_l3tt3r(msg:str)->str:
    new_message = ""
    for letters in msg:
        if letters == 'a':
            new_message += '4'
        elif letters == 'e':
            new_message += '3'
        elif letters == 'i':
            new_message += '1'
        elif letters == 'I':
            new_message += '1'
        elif letters == 'o':
            new_message += '0'
        elif letters == ' ':
            new_message += '_'
        else:
            new_message += letters
    return new_message
case1 = get_l3tt3r("Hello World")
print(case1)
case2 = get_l3tt3r("Why did I choose CS?")
print(case2)
case3 = get_l3tt3r("Remember the figure caption")
print(case3)
```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz19.png)
## Flow Diagram
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/19.jpg)
## Part B
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/19b.jpg)
