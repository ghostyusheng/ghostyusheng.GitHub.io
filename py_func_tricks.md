# python function tricks

### rfind
We all know 'find' is used to index the position of a specific string.
However, sometimes we need to find the last substring's position of a string.
If we forget this function, it takes a lot of pain.

For instance, there is a simple algorithem question?
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
