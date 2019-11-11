# sem3-t3
Тема 3. Строки. Байты. Файлы
## Инвариантная СР
###
###
###
###
## Вариативная СР
### 3.1. Реализовать программу-игру «Угадай число», в которой для вывода на экран информации использовать метод format. 
```python
import random
min_n = int(input('Enter the min number\n'))
max_n = int(input('Enter the max number\n'))
prog_n = random.randint(min_n, max_n)
print('Hah, try to guess my number!!!!')
while (True):
    user_n = int(input('Enter the number what you guess\n'))
    if (user_n == prog_n):
        print('Yeah, you are right, lucky boy. My number was {0}'.format(user_n))
        break;
    else:
        if (user_n > prog_n):
            print('Hahaahahaha, {0} is wrong! My number is less than yours'.format(user_n))
        else:
            print('Hahaahahaha, {0} is wrong! My number is bigger than yours'.format(user_n))
```
### 3.2. Реализовать программу шифрующую строку, задаваемую пользователем, с помощью алгоритма шифрования, использующего сдвиг на определенное количество знаков (шифр Цезаря). Сдвиг задается пользователем.
```python
def crypto(string, delt=4):
    UA = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
    LA = 'abcdefghijklmnopqrstuvwxyz'
    res = ''
    for i in string:
        if (i.islower()):
            res += LA[(LA.index(i) + delt) % len(LA)]
        else:
            res += UA[(UA.index(i) + delt) % len(UA)]
    return res
a = int(input('Enter the shift value\n'))
assert(crypto('exxegoexsrgi', 1) == 'fyyfhpfytshj')
assert(crypto('exxegoexsrgi', 2) == 'gzzgiqgzutik')
assert(crypto('exxegoexsrgi', 3) == 'haahjrhavujl')
assert(crypto('exxegoexsrgi', 4) == 'ibbiksibwvkm')
assert(crypto('exxegoexsrgi', 5) == 'jccjltjcxwln')
assert(crypto('exxegoexsrgi', 6) == 'kddkmukdyxmo')
assert(crypto('exxegoexsrgi', 7) == 'leelnvlezynp')
assert(crypto('exxegoexsrgi', 8) == 'mffmowmfazoq')
assert(crypto('exxegoexsrgi', 9) == 'nggnpxngbapr')
print(crypto('exxegoexsrgi', a))
```
