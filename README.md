# sem3-t3
Тема 3. Строки. Байты. Файлы
## Инвариантная СР
### 3.1. Создание аннотированного списка библиотек для работы с текстом в Python. Формирование отчета по выполнению задания и размещение его в портфолио, персональном репозитории. 
### 3.2. Разработка сценария с реализацией операции поиска подстроки в тексте.
```python
input_str = input("Enter source string:\n")
searchable_str = input("Enter the substring:\n")
try:
    print("Your substring beginning from letter number : {0}".format(input_str.index(searchable_str) + 1))
except ValueError:
    print('I can`t find this substring!')

```
### 3.3. Создание скрипта для считывания данных справочных логов из текстового файла и преобразования их в CSV-формат с последующей записью в новый файл. Формирование отчета по выполнению задания и размещение его в портфолио, персональном репозитории.
```python
import json
file = open("res.csv", "w")
with open("data.json", "r") as read_file:
    data = json.load(read_file)
for strin in data:
    res_str = ''
    for i in strin.values():
        res_str += "{0};".format(i)
    file.write(res_str[:len(res_str) - 1] + "\n")
file.close()
```
![Результат](https://github.com/python-basic/sem3-t3-TsirulikIvan/blob/master/yrIoPg8r17E.jpg)

### 3.4. Реализовать программу шифрующую строку, задаваемую пользователем, с помощью алгоритма шифрования ROT13. Формирование отчета по выполнению задания и размещение его в портфолио, персональном репозитории.
```python
def crypto(string, delt=13):
    UA = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
    LA = 'abcdefghijklmnopqrstuvwxyz'
    res = ''
    for i in string:
        if (i.islower()):
            res += LA[(LA.index(i) + delt) % len(LA)]
        else:
            res += UA[(UA.index(i) + delt) % len(UA)]
    return res
print(crypto('exxegoexsrgi'))
```
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
