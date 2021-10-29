---
## Front matter
lang: ru-RU
title: Отчёт по лабораторной работе 4
author: 'Дзугаева Лилия Владиславовна'

## Formatting
toc: false
slide_level: 2
theme: metropolis
mainfont: PT Serif 
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

## Цель работы

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

## Задание

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

## {.standout}

Спасибо за внимание