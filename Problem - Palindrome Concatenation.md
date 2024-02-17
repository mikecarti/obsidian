Палиндром – это строка, которая одинаково читается как слева направо, так и справа налево.

Дан набор из n строк (1 ≤ n ≤ 105). Найдите среди них такие пары, которые при конкатенации дают палиндром. Более формально, найдите все пары (i, j) такие, что i ≠ j и строка si+sj является палиндромом.

Выведите все упорядоченные пары индексов (нумерация с единицы).

```python
def is_palindrome(s):  
    return s == s[::-1]  
  
n = int(input())  
  
strings = []  
for i in range(n):  
    strings.append(str(input()))  
  
words = {w: i+1 for (i,w) in enumerate(strings)}  
palindromes = []  
  
# Time complexity O(n*k^2) n - length of word, k - length of longest word  
for word, i in words.items():  
    for j in range(0, len(word) + 1):  
        suf = word[j:]  
        pref = word[:j]  
  
        if is_palindrome(pref):  
            reverse_suffix = suf[::-1]  
            # if words.get(reverse_suffix) is not None and reverse_suffix != word:            if words.get(reverse_suffix) is not None and reverse_suffix != word:  
                palindromes.append((words.get(reverse_suffix), i))  
        if is_palindrome(suf) and j != len(word):  
            reverse_prefix = pref[::-1]  
            if words.get(reverse_prefix) is not None and reverse_prefix != word:  
                palindromes.append((i, words.get(reverse_prefix)))  
  
palindromes = sorted(palindromes)  
for x,y in palindromes:  
    print(x,y)
```