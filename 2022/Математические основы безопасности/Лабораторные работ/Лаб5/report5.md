---
# Front matter 
lang: ru-RU
title: "Лабораторная работа №5"
subtitle: "Вероятностное определение простоты числа"
author: "Пак Мария НФИ-02-22"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text

---

# Лабораторная работа №5

[TOC]

## Цель работы
 Реализовать с помощью программирования программы определяющие отношение к составным или простым числам, методами, описанными в задании к лабораторной работе №5.

## Задание

Разработать программы, которые будут представлять из себя: 

1. Программа повторяющая тест Ферма. 
2. Программа повторяющая тест Соловея-Штрассена  (алгоритм Якоби будет его частью)
3. Тест Миллера-Рабина

## Теоретическое введение

Поскольку определение простоты чисел является актуальной задачей криптографии, математиками разработано большое количество алгоритмов, которые с высокой эффективностью за ограниченное время позвляют проверить число на простоту: *тест Миллера, Миллера-Рабина, Люка-Лемера, Пепина, Агравала-Каяла-Саксены, Соловея-Штрассена* и другие [[1]](## Список литературы).

При проверке числа на простоту тестом Ферма выбирают несколько чисел a. Чем больше количество a, для которых утверждение истинно, тем больше вероятность, что число n простое. Однако существуют составные числа, для которых данное равенство выполняется для всех a взаимно простых с - это числа Кармайкла. Чисел Кармайкла — бесконечное множество, наименьшее число Кармайкла — 561. Тем не менее, тест Ферма довольно эффективен для обнаружения составных чисел.[[2]](## Список литературы)

Тест Миллера — Рабина — вероятностный полиномиальный тест простоты. Тест Миллера — Рабина позволяет эффективно определять, является ли данное число составным. Однако, с его помощью нельзя строго доказать простоту числа. Тем не менее тест Миллера — Рабина часто используется в криптографии для получения больших случайных простых чисел.[[3]](## Список литературы).

## Оборудование

Лабораторная работа выполнялась дома со следующими характеристиками техники: 

– Intel(R) Core(TM) i7-7700HQ CPU @ 2.80GHz 2.81GHz
– ОС Майкрософт Windows 10
– VirtualBox верс. 6.1.26

# Выполнение лабораторной работы

 1. Реализовала программу определения простоты чисел по алгоритму Теста Ферма.

      (рис. -@fig:001)
      ![Тест Ферма](image/rep1.png){ #fig:001 width=100% }

      Основная суть алгоритма лежит в том, чтобы сравнить число n (определяемое), c произвольным числом а (1<a<n-1). 

      Как видно на слайде, алгоритм в данном случае верно определяет, что число составное.

      2. Реализовала программу Миллера-Рабина.
      
         (рис. -@fig:003)
         ![Тест Миллера-Рабина](image\rep2.png){ #fig:001 width=100% }

         Тест Миллера — Рабина, наряду с тестом Ферма и тестом Соловея — Штрассена, позволяет эффективно определить, является ли данное число составным. Однако, с его помощью нельзя строго доказать простоту числа. Тем не менее тест Миллера — Рабина часто используется в криптографии для получения больших случайных простых чисел.

         Как мы видим, здесь алгоритм также верно определил, что цифра 15 является составным числом.

      3. Реализовала алгоритм Соловея-Штрассена. (рис. -@fig:005)
         ![Тест Соловея-Штрассена](image\rep3.png){ #fig:001 width=100% }

         Тест всегда корректно определяет, что простое число является простым, но для составных чисел с некоторой вероятностью он может дать неверный ответ. Основное преимущество теста заключается в том, что он, в отличие от теста Ферма, распознает числа Кармайкла как составные. Также в этом алгоритме рассчитывается число Якоби, как часть программы.

         Как мы видим, тут также алгоритм верно определил, что число является составным.

      

## Выводы
Освоила на практике написание алгоритмов проверки чисел на простоту.

## Список литературы 

1. Алгоритм Ферма // Wikipedia URL: https://ru.wikipedia.org/wiki/%D0%90%D0%BB%D0%B3%D0%BE%D1%80%D0%B8%D1%82%D0%BC_%D0%95%D0%B2%D0%BA%D0%BB%D0%B8%D0%B4%D0%B0 (дата обращения: 24.12.2021).
2. Метода нахождения простых чисел // ФоксФОРД URL: https://foxford.ru/wiki/matematika/prostye_chisla (дата обращения: 25.12.2021).
3. Тест Миллера-Рабина // Наука клубТ URL:  https://nauka.club/matematika/test-Miller.html (дата обращения: 27.10.2021).





