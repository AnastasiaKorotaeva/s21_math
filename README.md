# s21_math

Реализация собственной версии математической библиотеки math.h.

![s21_math](/images/logo.jpeg)

## Содержание

1. [Краткое описание](#Краткое-описание)  
2. [Команда разработки проекта](#Команда-разработки-проекта) 
3. [Обзор некоторых функций "math.h"](#Обзор-некоторых-функций-"math.h") 
4. [Реализация функций библиотеки math.h](#Реализация-функций-библиотеки-math.h) 
5. [Установка](#Установка)  

## Краткое описание  

В данном проекте разработана собственная версия стандартной библиотеки math.h на языке программирования Си. Эта библиотека реализует базовые математические операции, которые затем используются в различных алгоритмах. 


## Команда разработки проекта

Над реализацией проекта работали:

| Никнейм   | Имя       | Роль                                                       |
|-----------|-----------|------------------------------------------------------------|
| tamramar  | Анастасия | алгебраические выражения (кроме log, exp, pow)             |
| kidneyha  | Олег      | тестирование, log, exp, pow                                |
| craydlec  | Раниль    | тригонометрия                                              |
| tuppngan  | Роберт    | работа с краевыми значениями, обработка ошибок             | 

### Обзор некоторых функций "math.h"

Математические операции на языке Си представляют собой группу функций в стандартной библиотеке языка программирования Си, реализующих основные математические функции. Все функции так или иначе используют числа с плавающей запятой. Различные стандарты C предоставляют различные, хотя и обратно совместимые, наборы функций. Любые функции, которые работают с углами, используют радианы в качестве единицы измерения угла. 

| No. | Function | Description |
| --- | -------- | ----------- |
| 1 | `int abs(int x)` | вычисляет абсолютное значение целого числа |
| 2 | `long double acos(double x)` | вычисляет арккосинус |
| 3 | `long double asin(double x)` | вычисляет арксинус |
| 4 | `long double atan(double x)` | вычисляет арктангенс |
| 5 | `long double ceil(double x)` | возвращает ближайшее целое число, не меньшее заданного значения |
| 6 | `long double cos(double x)` | вычисляет косинус |
| 7 | `long double exp(double x)` | возвращает значение e, возведенное в заданную степень |
| 8 | `long double fabs(double x)` | вычисляет абсолютное значение числа с плавающей точкой |
| 9 | `long double floor(double x)` | возвращает ближайшее целое число, не превышающее заданное значение |
| 10 | `long double fmod(double x, double y)` | остаток операции деления с плавающей точкой |
| 11 | `long double log(double x)` | вычисляет натуральный логарифм |
| 12 | `long double pow(double base, double exp)` | возводит число в заданную степень |
| 13 | `long double sin(double x)` | вычисляет синус |
| 14 | `long double sqrt(double x)` | вычисляет квадратный корень |
| 15 | `long double tan(double x)` | вычисляет тангенс |  

## Реализация функций библиотеки math.h

В ходе проекта было выполнено:
1. Реализованы функции библиотеки math.h (только те, что непосредственно описаны [выше](#обзор-некоторых-функций-mathh))
2. Библиотека разработана на языке Си стандарта C11 с использованием компиятора gcc 
3. При написании кода придерживались Google Style
4. Решение оформлено как статическая библиотека (с заголовочным файлом s21_math.h)
5. Библиотека разработана в соответствии с принципами структурного программирования, исключено дублирование кода
6. Перед каждой функцией использован префикс s21_
7. Подготовлено полное покрытие unit-тестами функций библиотеки c помощью библиотеки Check
8. Unit-тесты проверяют результаты работы реализации путём сравнения ее с реализацией стандартной библиотеки math.h
9. В цели gcov_report формируется отчёт gcov в виде html страницы. 
10. Предусмотрен Makefile для сборки библиотеки и тестов (с целями all, clean, test, s21_math.a, gcov_report)  
11. Общая проверяемая точность - 16 значащих цифр
12. Проверяемая точность дробной части - максимум 6 знаков после запятой.

## Установка

Чтобы пользоваться программой, необходимо зайти в папку src и с помощью команд выполнить необходимые действия:

`make all` - Эта цель запускает цель `s21_math.a`

`make test` - Эта цель компилирует и запускает тестовый файл s21_math_test.c, который,содержит набор тестов для библиотеки s21_math.a

`make s21_math.a` - Эта команда создает статическую библиотеку из исходных файлов

`make gcov_report` - Эта команда создает отчет о том, как много кода покрыто тестами. Она компилирует файлы с опцией для сбора данных о покрытии кода. Затем она создает отчет, который вы можете просмотреть в веб-браузере.

`make style` - Эта команда проверяет на googlestyle

`make clean` - Эта команда удаляет временные файлы, созданные в процессе сборки программы.

`make clean_test` - Эта команда удаляет временные файлы после выполнения тестов.
