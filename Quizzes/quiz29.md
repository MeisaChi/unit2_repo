## Part A
```.py
def count_letters(my_dict, msg):
    for letters in msg:
        if letters in my_dict.keys():
            my_dict[letters] += 1
    return my_dict

vowels = {'a':0, 'i':0, 'e':0, 'o':0, 'u':0}
test1 = count_letters(my_dict=vowels, msg="hello world")
print(test1)
test2 = count_letters(my_dict=vowels, msg="why did I choose computer science?")
print(test2)
```
![](https://github.com/MeisaChi/unit2_repo/blob/main/Screenshots/quiz29.png)
## Part B
2⁶ = 64 colors
