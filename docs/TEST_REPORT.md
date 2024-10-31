# Модульное негативное функциональное white box тестирование python библиотеки geometric_lib
## Библиотека geometric_lib прошла Smoke тесты от [GuySky](https://github.com/GuySky)
   
   
### Тестируемые модули
В каждом файле библиотеки был прописан класс, содержащий в себе модульные тесты для каждой функции в файле. То есть, было выполнено ручное white box тестирование. 
   
### Требования
В данном случае требования от функций были достаточно тривиальны - находить площадь и периметр для выбранной фигуры. Более конкретно: для фигуры по её названию выбирается файл из существующих, далее, если нужно посчитать площадь или периметр фигуры, выбирается функция area для площади или perimeter для периметра, на вход подаются соответствующие аргументы. 
   
### Процесс и направления тестирования
В процессе тестирования планировалось проверить, соответствует ли вывод программы интуитивным ожиданиям. Если не соответствует, то для каких входных данных не соответствует, и что выдаёт.   
   
### Критерии прохождения теста
Тест считается пройденным в единственном случае: если результаты работы функции на 100% соответствуют ожидаемым. Результаты проверяются на соответствие с помощью встроенной python библиотеки unittest. Если вердикт указан как ОКsup{1}
   
## Результаты тестирования
| Тестируемый модуль | Назначение теста | Входные данные | Ожидаемый результат | Фактический результат | Вердикт |
|--------------------|------------------|----------------|---------------------|-----------------------|---------|
| `rectangle.area` | Сторона прямоугольника равна нулю/Взаимодействие функции с нулём | `(10, 0)` | `0` | `0` | ОК |
| `rectangle.area` | На вход поданы равные длины сторон | `(10, 10)` | `100` | `100` | ОК |
| `rectangle.area` | Сторона прямоугольника равна единице | `(10, 1)` | `10` | `10` | ОК |
| `rectangle.area` | Проверка взаимодействия с положительными числами | `(10, 5)` | `50` | `50` | ОК |
| `rectangle.area` | Проверка взаимодействия с отрицательными числами | `(10, -10)` | `-100` | `-100` | ОК^[1][1] |
| `rectangle.area` | Проверка взаимодействия с дробными числами | `(10, 0.5)` | `5` | `5` | ОК |
| `rectangle.area` | Проверка взаимодействия со строками | `(10, 'abc')` | `abcabcabcabcabcabcabcabcabcabc` | `abcabcabcabcabcabcabcabcabcabc` | ОК^[2][2] |
| `rectangle.perimeter` | Сторона прямоугольника равна нулю/Взаимодействие функции с нулём | `(10, 0)` | `20` | `20` | ОК |
| `rectangle.perimeter` | На вход поданы равные длины сторон | `(10, 10)` | `40` | `40` | ОК |
| `rectangle.perimeter` | Сторона прямоугольника равна единице | `(10, 1)` | `22` | `22` | ОК |
| `rectangle.perimeter` | Проверка взаимодействия с положительными числами | `(10, 5)` | `30` | `30` | ОК |
| `rectangle.perimeter` | Проверка взаимодействия с отрицательными числами | `(10, -10)` | `0` | `0` | ОК^[1][1] |
| `rectangle.perimeter` | Проверка взаимодействия с дробными числами | `(10, 0.5)` | `21` | `21` | ОК |
| `rectangle.perimeter` | Проверка взаимодействия со строками | `(10, 'abc')` | `TypeError` | `TypeError` | ОК^[3][3] |
| `circle.area` | Радиус круга равен нулю/Взаимодействие функции с нулём | `(0)` | `0` | `0` | ОК |
| `circle.area` | Радиус круга равен единице | `(1)` | `3.141592653589793` | `3.141592653589793` | ОК |
| `circle.area` | Проверка взаимодействия с положительными числами | `(10)` | `314.1592653589793` | `314.1592653589793` | ОК |
| `circle.area` | Проверка взаимодействия с отрицательными числами | `(-10)` | `314.1592653589793` | `314.1592653589793` | ОК^[1][1] |
| `circle.area` | Проверка взаимодействия с дробными числами | `(0.5)` | `0.7853981633974483` | `0.7853981633974483` | ОК |
| `circle.area` | Проверка взаимодействия со строками | `('abc')` | `TypeError` | `TypeError` | ОК^[3][3] |
| `circle.perimeter` | Радиус круга равен нулю/Взаимодействие функции с нулём | `(0)` | `0` | `0` | ОК |
| `circle.perimeter` | Радиус круга равен единице | `(1)` | `6.283185307179586` | `6.283185307179586` | ОК |
| `circle.perimeter` | Проверка взаимодействия с положительными числами | `(10)` | `62.83185307179586` | `62.83185307179586` | ОК |
| `circle.perimeter` | Проверка взаимодействия с отрицательными числами | `(-10)` | `-62.83185307179586` | `-62.83185307179586` | ОК^[1][1] |
| `circle.perimeter` | Проверка взаимодействия с дробными числами | `(0.5)` | `3.141592653589793` | `3.141592653589793` | ОК |
| `circle.perimeter` | Проверка взаимодействия со строками | `('abc')` | `TypeError` | `TypeError` | ОК^[3][3] |
| `square.area` | Сторона квадрата равна нулю/Взаимодействие функции с нулём | `(0)` | `0` | `0` | ОК |
| `square.area` | Сторона квадрата равна единице | `(1)` | `1` | `1` | ОК |
| `square.area` | Проверка взаимодействия с положительными числами | `(10)` | `100` | `100` | ОК |
| `square.area` | Проверка взаимодействия с отрицательными числами | `(-10)` | `100` | `100` | ОК^[1][1] |
| `square.area` | Проверка взаимодействия с дробными числами | `(0.5)` | `0.25` | `0.25` | ОК |
| `square.area` | Проверка взаимодействия со строками | `('abc')` | `TypeError` | `TypeError` | ОК^[3][3] |
| `square.perimeter` | Сторона квадрата равна нулю/Взаимодействие функции с нулём | `(0)` | `0` | `0` | ОК |
| `square.perimeter` | Сторона квадрата равна единице | `(1)` | `4` | `4` | ОК |
| `square.perimeter` | Проверка взаимодействия с положительными числами | `(10)` | `40` | `40` | ОК |
| `square.perimeter` | Проверка взаимодействия с отрицательными числами | `(-10)` | `-40` | `-40` | ОК^[1][1] |
| `square.perimeter` | Проверка взаимодействия с дробными числами | `(0.5)` | `2` | `2` | ОК |
| `square.perimeter` | Проверка взаимодействия со строками | `('abc')` | `abcabcabcabc` | `abcabcabcabc` | ОК^[2][2] |
| `triangle.area` | Одна из сторон треугольника равна нулю/Взаимодействие функции с нулём | `(0, 10)` | `0` | `0` | ОК |
| `triangle.area` | Высота треугольника равна нулю/Взаимодействие функции с нулём | `(10, 0)` | `0` | `0` | ОК |
| `triangle.area` | Одна из сторон треугольника равна единице | `(1, 10)` | `5` | `5` | ОК |
| `triangle.area` | Высота треугольника равна единице | `(10, 1)` | `5` | `5` | ОК |
| `triangle.area` | Проверка взаимодействия с положительными числами | `(10, 10)` | `50` | `50` | ОК |
| `triangle.area` | Проверка взаимодействия с отрицательными числами | `(-10, 10)` | `-50` | `-50` | ОК^[1][1] |
| `triangle.area` | Проверка взаимодействия с дробными числами | `(10, 0.5)` | `2.5` | `2.5` | ОК |
| `triangle.area` | Проверка взаимодействия со строками (сторона) | `('abc', 10)` | `TypeError` | `TypeError` | ОК^[3][3] |
| `triangle.area` | Проверка взаимодействия со строками (высота) | `(10, 'abc')` | `TypeError` | `TypeError` | ОК^[3][3] |
| `triangle.perimeter` | Все стороны треугольника равны нулю/Взаимодействие функции с нулём | `(0, 0, 0)` | `0` | `0` | ОК |
| `triangle.perimeter` | Все стороны треугольника равны единице | `(1, 1, 1)` | `3` | `3` | ОК |
| `triangle.perimeter` | Проверка взаимодействия с положительными числами | `(10, 10, 10)` | `30` | `30` | ОК |
| `triangle.perimeter` | Проверка взаимодействия с отрицательными числами | `(-10, -10, -10)` | `-30` | `-30` | ОК^[1][1] |
| `triangle.perimeter` | Проверка взаимодействия с дробными числами | `(0.5, 0.5, 0.5)` | `1.5` | `1.5` | ОК |
| `triangle.perimeter` | Проверка взаимодействия со строками | `('abc', 'abc', 'abc')` | `abcabcabc` | `abcabcabc` | ОК^[2][2] |
   
[1]: Работа с отрицательными числами может быть контринтуитивна, так как предлагается работа с отрицательными длинами, однако это может быть полезно, например, при работе с графическими библиотеками.   
[2]: Работа со строками тоже может быть контринтуитивна, но это может иметь смысл. Если отрезок можно представить как последовательность букв, с ним всё ещё можно работать.   
[3]: Некоторые функции работают со строками, некоторые - нет. Это понятно, если знать, как работает умножение чисел на строки, и если знать, что строки на числа в python не делятся. То есть, в функциях, где есть деление аргументов, аргументы в качестве строк вызывают ошибку.