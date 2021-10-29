---
# Front matter
title: "Отчёт по лабораторной работе"
subtitle: "Лабораторная работа 4"
author: "Дзугаева Лилия Владславовна"

# Generic otions
lang: ru-RU

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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
## Misc options
indent: true
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
  - \usepackage  # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

# Задание

Лабораторная работа подразумевает работу с виртуальной машиной _VirtualBox_ операционной системы _Linux_, дистрибутив _Centos_, с консолью и с расширенными атрибутами файлов.

# Выполнение лабораторной работы

1. От имени пользователя guest определила расширенные атрибуты файла _/home/guest/dir1/file1_ с помощью команды _lsattr /home/guest/dir1/file1_ (рис. 1):

![рис. 1. Расширенные атрибуты файла](image/1.jpg){ #fig:001 width=70% }

2. Установила командой _chmod 600 file1_ на файл file1 права, разрешающие чтение и запись для владельца файла. (рис. 2)

![рис. 2. Установка прав на файл](image/2.jpg){ #fig:001 width=70% }

3. Попробовала установить на файл _/home/guest/dir1/file1_ расширенный атрибут _a_ от имени пользователя guest с помощью команды _chattr +a /home/guest/dir1/file1_ (рис. 3). Получила отказ от выполнения операции.

![рис. 3. Установка расширенного атрибута](image/3.jpg){ #fig:001 width=70% }

4. С помощью команды su повысила свои права. Установила расширенный атрибут _а_ на файл /home/guest/dir1/file1_ от имени суперпользователя с помощью команды: _chattr +a /home/guest/dir1/file1_ (рис. 4)

![рис. 4. Установка расширенного атрибута](image/4.jpg){ #fig:001 width=70% }

5. От пользователя _guest_ проверила правильность установления атрибута с помощью команды _lsattr /home/guest/dir1/file1_ (рис. 5)

![рис. 5. Правильность установления атрибута](image/5.jpg){ #fig:001 width=70% }

6. Выполнила дозапись в файл file1 слова “test” с помощью команды _echo “test” /home/guest/dir1/file1_ (рис. 6)

![рис. 6. Дозапись в файл](image/6.1.jpg){ #fig:001 width=70% }

7. Попробовал стереть имеющуюся информацию в файле с помощью команды _echo «abcd» > /home/guest/dir1/file1_ (рис. 7.1)

![рис. 7.1. Удаление информации в файле](image/7.1.jpg){ #fig:001 width=70% }

    Попробовала переименовать файл, но получила отказ (рис. 7.2)

![рис. 7.2. Изменение имени файла](image/7.2.jpg){ #fig:001 width=70% }

8. Попробовала с помощью команды _chmod 000 file1_ установить на файл file1 права, например, запрещающие чтение и запись для владельца файла. Не удалось выполнить. (рис. 8)

![рис. 8. Установка прав](image/8.jpg){ #fig:001 width=70% }

9. Сняла расширенный атрибут _а_ с файла _/home/guest/dir1/file1_ от имени суперпользователя с помощью команды _chattr -a /home/guest/dir1/file1_. Повторила операции, которые ранее не удалось выполнить. (рис. 9)

![рис. 9. Снятие расширенного атрибута](image/9.jpg){ #fig:001 width=70% }

10. Повторила все действия по шагам, заменив атрибут «а» атрибутом «i» (рис. 10)

![рис. 10. Повтор шагов](image/10.jpg){ #fig:001 width=70% }

  Удаляем атрибут i и дозаписываем информацию в файл (рис. 10.1)

![рис. 10.1. Удаление атрибута](image/10.1.jpg){ #fig:001 width=70% }

# Выводы

Во время выполнения данной лабораторной работы я повысила свои навыки использования интерфейса командной строки (CLI), познакомилась на примерах с тем, как используются основные и расширенные атрибуты при разграничении доступа. Я имела возможность связать теорию дискреционного разделения доступа с ее реализацией на практике в OC Linux. Так же опробовала действие на практике расширенных атрибутов «а» и «i».

# Список литературы{.unnumbered}

::: {#refs}
:::
