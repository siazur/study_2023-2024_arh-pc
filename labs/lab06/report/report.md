---
## Front matter
title: "Лабораторная работа 6"
subtitle: ""
author: "Мазуркевич Анастасия Дмитриевна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Освоение арифметических инструкций языка ассемблера NASM.

# Задание


# Выполнение лабораторной работы

1. Создайте каталог для программам лабораторной работы № 6, перейдите в него и
создайте файл lab6-1.asm:

![создаем каталог](image/6.1.jpg){#fig:001 width=70%}

Введите в файл lab6-1.asm текст программы из листинга 6.1

![вводим](image/6.2.jpg){#fig:002 width=70%}

Создайте исполняемый файл и запустите его.

![создаем и запускаем](image/6.3.jpg){#fig:003 width=70%}

Далее изменим текст программы и вместо символов, запишем в регистры числа. Исправьте текст программы (Листинг 6.1) следующим образом: замените строки

![заменяем строки](image/6.4.jpg){#fig:004 width=70%}

Создайте исполняемый файл и запустите его. Отображается ли символ? Нет, не отображается

![проверяем работу файла](image/6.5.jpg){#fig:005 width=70%}

Создайте файл lab6-2.asm в каталоге ~/work/arch-pc/lab06 и введите в него текст программы из листинга 6.2.

![создаем](image/6.6.jpg){#fig:006 width=70%}

![вводим код из листинга](image/6.7.jpg){#fig:007 width=70%}

Создайте исполняемый файл и запустите его.

![запускаем](image/6.8.jpg){#fig:008 width=70%}

Аналогично предыдущему примеру изменим символы на числа. Замените строки

![заменяем строки](image/6.9.jpg){#fig:009 width=70%}

Создайте исполняемый файл и запустите его. Какой результат будет получен при исполнении программы? Резутьтат - 10

![создаем и проверяем](image/6.10.jpg){#fig:010 width=70%}

Замените функцию iprintLF на iprint. Создайте исполняемый файл и запустите его. Чем
отличается вывод функций iprintLF и iprint? Разница в переносе строки

![заменяем строки](image/6.11.jpg){#fig:011 width=70%}

![проверяем](image/6.12.jpg){#fig:012 width=70%}

Создайте файл lab6-3.asm в каталоге ~/work/arch-pc/lab06

![создаем](image/6.13.jpg){#fig:013 width=70%}

Внимательно изучите текст программы из листинга 6.3 и введите в lab6-3.asm.

![вводим листинг](image/6.14.jpg){#fig:014 width=70%}

Создайте исполняемый файл и запустите его.

![создаем и запускаем, результат верный](image/6.15.jpg){#fig:015 width=70%}

Измените текст программы для вычисления выражения 𝑓(𝑥) = (4 ∗ 6 + 2)/5

![изменяем](image/6.16.jpg){#fig:016 width=70%}

Создайте исполняемый файл и проверьте его работу

![проверяем, все верно](image/6.17.jpg){#fig:017 width=70%}

Создайте файл variant.asm в каталоге ~/work/arch-pc/lab06:

![создаем](image/6.18.jpg){#fig:018 width=70%}

Внимательно изучите текст программы из листинга 6.4 и введите в файл variant.asm.

![вводим листинг](image/6.19.jpg){#fig:019 width=70%}

Проверьте работу файла, получите ваш вариант

![работает, 4 вариант](image/6.20.jpg){#fig:020 width=70%}


Включите в отчет по выполнению лабораторной работы ответы на следующие вопросы:
1. Какие строки листинга 6.4 отвечают за вывод на экран сообщения ‘Ваш вариант:’?
mov eax,rem
call sprint
2. Для чего используется следующие инструкции?
mov ecx, x
mov edx, 80
call sread 
Для чтения строки с данными, которые вводит пользователь

3. Для чего используется инструкция “call atoi”?
Используется для преобразования строки в целое
число. Принимает адрес строки в регистре eax и возвращаетполученное
число в регистре eax.

4. Какие строки листинга 6.4 отвечают за вычисления варианта?
Строка “xor edx,edx” обнуляет регистр edx перед делением.
“mov ebx,20” загружает значение 20 в ebx. “div ebx” деление eax на значение регистра ebx с сохранением
частного в регистре eax и остатка в регистре edx.

5. В какой регистр записывается остаток от деления при выполнении инструкции “div
ebx”?
Остаток от деления записывается в регистр edx.

6. Для чего используется инструкция “inc edx”?
Для увеличения значения в регистре edx
на 1. В данном случае увеличивает остаток от деления на 1

7. Какие строки листинга 6.4 отвечают за вывод на экран результата вычислений?
“mov eax,edx” передает значение остатка от деления в регистр eax.
“call iprintLF” вызывает процедуру iprintLF для вывода значения на
экран вместе с переводом строки.

САМОСТОЯТЕЛЬНАЯ РАБОТА
Написать программу вычисления выражения 𝑦 = 𝑓(𝑥). Программа должна выводить
выражение для вычисления, выводить запрос на ввод значения 𝑥, вычислять заданное выражение в зависимости от введенного 𝑥, выводить результат вычислений. Вид
функции 𝑓(𝑥) выбрать из таблицы 6.3 вариантов заданий в соответствии с номером
полученным при выполнении лабораторной работы. Создайте исполняемый файл и
проверьте его работу для значений 𝑥1 и 𝑥2 из 6.3.

Для начала создадим новый файл

![создаем файл](image/6.21.jpg){#fig:022 width=70%}

Пишем программу для вычисления функции

![код](image/6.22.jpg){#fig:022 width=70%}

Проверяем для х=4

![все верно](image/6.23.jpg){#fig:023 width=70%}

Проверяем для х=10

![все верно](image/6.24.jpg){#fig:024 width=70%}


# Выводы

Освоили арифметические инструкции языка ассемблера NASM.

# Список литературы{.unnumbered}

::: {#refs}
:::
