# Вопросы на тему программирования

Софт скилы
----------

1. Скажите мне, как бы вы преодолели ситуацию, когда команда плохо работает, потому что члены не ладят.
2. Что для вас значит командный дух и как бы вы его построили?
3. Как бы вы справились с товарищем по команде, который не выполнял свою долю работы?
4. Вы знаете, что ваш менеджер на 100% неправ в чем-то. Что вы сделаете?
5. Как вы относитесь к делегированию обязанностей в команде?
6. С каким самым трудным изменением вы столкнулись в своей карьере?
7. Как вы меняете свое расписание, если происходит что-то незапланированное?
8. Приведите пример, когда вы успешно решили проблему.
9. Приведите пример, когда вам приходилось проявлять творческий подход или нестандартность в решении проблемы.
10. Как вы сохраняете мотивацию, работая в одиночку над проектом?
11. Чего вы надеетесь достичь в течение первых шести месяцев работы в нашей компании?
12. Вам нравится ответственность за принятие решений или вы бы предпочли оставить это кому-то другому?
13. Что заставит вас бросить работу в первый месяц?

Python
------
**1. В чем разница между списком и кортежем?**

Ответ:
<ul>
    <li>Список можно изменить после создания.</li>
    <li>Кортеж нельзя изменить после создания.</li>
    <li>Кортеж хешируется, значит может использоваться как ключ в словаре</li>
    <li>Список не хешируется, значит не может быть использован как ключ в словаре</li>
</ul>

**2. Как выполняется интерполяция строк?**

Ответ:

```python
name = 'Chris'

# 1. f strings
print(f'Hello {name}')

# 2. % operator
print('Hey %s %s' % (name, name))

# 3. format
print(
 "My name is {}".format((name))
)
```

**3. В чем разница между "is" и "==" ?**

Ответ:

is проверяет идентичность, а == проверяет равенство.

```python
a = [1,2,3]
b = a
c = [1,2,3]
...
print(a == b)
print(a == c)
#=> True
#=> True
...
print(a is b)
print(a is c)
#=> True
#=> False
...
print(id(a))
print(id(b))
print(id(c))
#=> 4369567560
#=> 4369567560
#=> 4369567624
```

**4. Что такое декоратор?**

Ответ:

Декораторы – это обертка вокруг функций (или классов) в Python, которая меняет способ работы этой функции. Декоратор
абстрагирует свой собственный функционал.

```python
def decorator(func):
    def wrapper(*args, **kwargs):
        print("Hello, World!")
        func(*args, **kwargs)
    return wrapper

@decorator
def main():
    print("I'm here!")


main()
...
#=> Hello, World!
#=> I'm here!
```

**5. Объясните, как работает функция reduce**

Ответ:

reduce принимает функцию и последовательность — и проходит по этой последовательности. На каждой итерации в функцию
передаются как текущий элемент, так и выходные данные предыдущего элемента. В конце концов, возвращается одно значение:

```python
from functools import reduce


def add_three(x,y):
    return x + y
    
    
li = [1,2,3,5]

print(reduce(add_three, li))
...
#=> 11
```

**6. Объясните, как работает функция filter**

Ответ:

Функция делает буквально то, о чем говорит ее название: она фильтрует элементы в последовательности.

Каждый элемент передается функции, которая включает его в последовательность, если по условию получает True, и
отбрасывает в случае False:

```python 
def add_three(x):
    if x % 2 == 0:
        return True        
    return False

li = [1,2,3,4,5,6,7,8]

print([i for i in filter(add_three, li)])
...
#=> [2, 4, 6, 8]
```

**7. Переменные в Python передаются по ссылке или по значению?**

Ответ:

В Python аргументы передаются по ссылке, т. е. передается ссылка на реальный объект. 

Но есть два вида передачи объекта в
аргументах. 

* По значению: Передается копия реального объекта. Изменение значения копии объекта не приведет к изменению
значения исходного объекта. 
* По ссылке: Передается ссылка на реальный объект.

**8. В чем разница между глубокой и мелкой копиями?**

Ответ: 

* Глубокие копирования хранят копию значений объекта перечисляется, тогда как мелкая копия историй ссылка на исходный адрес памяти
* Глубокая копия не отражает изменений, внесенных в новый / скопированный объект в исходном объекте; тогда как неглубокая копия делает

Полное копирование: ```copy.deepcopy```

```python
import copy 

result_A = [[90, 85, 82], [72, 88, 90]]
result_B = copy.deepcopy(result_A)

result_B[0][0] = 30 

print(result_A) 
print(result_B) 
...
[[90, 85, 82], [72, 88, 90]] 
[[30, 85, 82], [72, 88, 90]] 
```

Поверхностное копирование: ```copy.copy```


```python
import copy 
 
result_A = [[90, 85, 82], [72, 88, 90]]
result_B = copy.copy(result_A) 
 
result_B[0][0] = 30 
 
print(result_A) 
print(result_B)
... 
[[30, 85, 82], [72, 88, 90]] 
[[30, 85, 82], [72, 88, 90]] 
```

**9. В чем разница между модулем и пакетом?**

Ответ:

Модуль — это файл или набор файлов, которые импортируются вместе:

```python
import sklearn
```

Пакет — это каталог с модулями:

```python
from sklearn import cross_validation
```

Таким образом, пакеты — это модули, но не все модули являются пакетами.
