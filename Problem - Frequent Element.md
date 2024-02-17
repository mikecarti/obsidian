Дан массив a из n целых чисел. Напишите программу, которая найдет число, которое встречается в массиве наибольшее число раз.

```python
n = int(input())  
  
elements = [int(x) for x in input().split(" ")]  
counts = {}  
max_occurrence_elements = ([], 0)  
  
for el in elements:  
    if counts.get(el) is None:  
        counts[el] = 1  
    else:  
        counts[el] += 1  
    list_of_frequent_elements = max_occurrence_elements[0]  
  
    if counts[el] > max_occurrence_elements[1]:  
        max_occurrence_elements = ([el], counts[el])  
    elif counts[el] == max_occurrence_elements[1]:  
        max_occurrence_elements = \  
            (list_of_frequent_elements + [el], counts[el])  
  
print(max(max_occurrence_elements[0]))
```