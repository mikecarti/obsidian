Диаграммой Юнга называется набор клеток, выровненный по левой границе, в котором длины строк образуют невозрастающую последовательность, если смотреть сверху вниз. Обозначается диаграмма списком длин ее строк в порядке невозрастания (сверху вниз).

Пример диаграммы (5, 4, 1):

![PIC](https://contest.yandex.ru/testsys/statement-image?imageId=dd065499bfc5651e58268df059d75639f39cf11bcbec70202a12f5ec4d2f5394)

Косым крюком длины k называется связная (по стороне клеток) часть клеток этой диаграммы, содержащая по ki≥0 правых клеток в каждой строке, ∑ki=k, и не содержащая внутри себя квадрата 2×2 из клеток, причем после удаления косого крюка из диаграммы Юнга должна остаться корректная диаграмма Юнга. Вот все косые крюки длины 5 для диаграммы Юнга выше.

![PIC](https://contest.yandex.ru/testsys/statement-image?imageId=0fe5ec7c732c29b920b312937d69702946c03f6de0c4e38d6e9265828f085dab)

![PIC](https://contest.yandex.ru/testsys/statement-image?imageId=731f7543ca95ca8183cb8eae23e63026e2a12820102fab6024f2b10c0e4aaad8)

Вам надо найти количество возможных крюков длины k для данной диаграммы.

```python
def young_diagram(k, cells_each_row):  
    if LOG: print(f"K: {k}, CELLS: {cells_each_row}")  
    # 1)  
    # convert rightmost snake to an array with special marks on    # first elements of every row    # 1.5)    # Mark cells that are above the marked one    tunnel = []  
    # for every row  
    for i, row in enumerate(cells_each_row):  
        # for cells from right to left  
        for j in range(row, 0, -1):  
            # mark the rightmost element  
            if j == row:  
                tunnel.append(1)  
            else:  
                tunnel.append(0)  
            # if not last row  
            if i != len(cells_each_row) - 1:  
                # if we should go down, then continue to next row  
                if j == cells_each_row[i + 1]:  
                    # if we go down, than we should mark that downward  
                    # has to be a marked cell                    tunnel[-1] += 2  
                    break  
    if LOG: print(tunnel)  
    # 2)  
    # Move a snake through this array and check, that it must    # start on a specially marked spot    # 3)    # count all such snakes that stand correctly    # Now we should also clarify, that snake does not end on a    # cell marked by 2, because it destroys young diagram    # 3.5) Assumption    # To have a snake, that when took away makes a Young Diagram,    #  We must also have a snake that never stops above the marked spot    #  If this condition is done, it will work    legal_ways_to_put_snake = 0  
    max_ways_to_put_snake = len(tunnel) - k + 1  
    for i in range(max_ways_to_put_snake):  
        if (tunnel[i] == 1 or tunnel[i] == 3) and tunnel[i + k - 1] < 2:  
            legal_ways_to_put_snake += 1  
            if LOG:  
                log_tunnel = ["x" if i <= j < i + k else orig for j, orig in enumerate(tunnel)]  
                print(f"i={i} Way to put snake: {log_tunnel}")  
    if LOG: print("\n")  
    return legal_ways_to_put_snake
```
