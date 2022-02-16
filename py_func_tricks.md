# python function tricks

### rfind
We all know 'find' is used to index the position of a specific string.
However, sometimes we need to find the last substring's position of a string.
If we forget this function, it takes a lot of pain.

For instance, there is a simple algorithm question?
There is a long string like 'xxx-xox-xxo-oox-oxx-xxo-oxx-xxx-xox-xxo-oox-oxx-xxo-oxx'.
Every pattern is made of a short string including 3 characters such as xxx, xxo, oxx.
Trying to find the last random pattern's position. For example, find the last position of 'xxo' .

Solution demo:
```markdown
"xxx-xox-xxo-oox-oxx-xxo-oxx".rfind('xxo')//4+1
```
Thought process:
1.We all know use 'rfind' to find the last substring's position.
2.Every pattern has 4 letters. 'xxx-', 'xox-'.
3.The string's total length // 4 + 1 is used to locate the pattern's position.


### dict.popitems
'dict.popitems' is used to pop the last item of a specific dictionary.
We can easily use this function to pump items from a dictionary as manipulating pipes and append logics we designed.

```markdown
profit_map = {
 'shoes': 15,
 'mouse': 10,
 'keyboard': 50
}

sum_profit = 0
while profit_map:
    item, profit = profit_map.popitem()
    print(item, profit)
    sum_profit += profit
print('sum profit:', sum_profit)

OUTPUT:
keyboard 50
mouse 10
shoes 15
sum profit: 75
```

### sort in complex collections
We all know to use SORT to sort a list, but we rarely use this function to sort complex collections.
There is an example of sorting the profit of a complex collection(dictionary list).

```
saled_items_dict_list = [
    {'product': 'shoes', 'profit': 18},
    {'product': 'mouse', 'profit': 11},
    {'product': 'keyboard', 'profit': 13},
]
saled_items_dict_list.sort(key=lambda i: i['profit'])
saled_items_dict_list

OUTPUT:
[{'product': 'mouse', 'profit': 11},
 {'product': 'keyboard', 'profit': 13},
 {'product': 'shoes', 'profit': 18}]
```

### str.maketrans
We can easily use this function to encrypt secret messages.
For instance.

```
ode_letter = "@#$%^&*()"
code_int = "812384651" 
pattern = str.maketrans(code_letter, code_int)
s = "Deer son! I'm going to die, my coffer's code is @&#^@&#. You know how to decrypt!"
s.translate(pattern)

OUTPUT:
"Deer son! I'm going to die, my coffer's code is 8418841. You know how to decrypt!"
```
