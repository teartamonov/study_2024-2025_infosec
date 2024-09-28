---
## Front matter
title: "Отчёт по лабораторной работе №4"
subtitle: "Дискреционное разграничение прав в Linux. Расширенные атрибуты"
author: "Артамонов Тимофей Евгеньевич"

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

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

# Теоретическое введение

chattr — команда, изменяющая атрибуты файлов на файловых системах ext2fs, ext3, ext4 и частично на других файловых системах Linux.
Операторы 
- "+" обозначает добавление указанных атрибутов к существующим
- "-" обозначает их снятие
- "=" обозначает установку только этих атрибутов файлам. [@wiki:bash]

Символы "ASacDdijsu" указывают на новые атрибуты файлов.

# Выполнение лабораторной работы

Попробуем добавить атрибут к файлу от имени записи guest. (рис. [-@fig:001])

![Получаем ошибку, поэтому делаем это от имени администратора](image/1.PNG){#fig:001 width=70%}

Посмотрим сработала ли команда. (рис. [-@fig:002])

![К файлу добавился атбрибут "a"](image/2.PNG){#fig:002 width=70%}

Попробуем различные действия с этим файлом. (рис. [-@fig:003])

![Сработала только команда чтения](image/3.PNG){#fig:003 width=70%}

Пробуем дальше. (рис. [-@fig:004])

![Несмотря на то, что владелец файла может читать и редактировать его по модификаторам доступа, мы не можем менять его как хотим](image/4.PNG){#fig:004 width=70%}

Пробуем дальше. (рис. [-@fig:005])

![Сработала только команда дозаписи в файл, то есть файл открыт только для добавления информации в него](image/5.PNG){#fig:005 width=70%}

Теперь снимем атрибут "a" и поставим "i". (рис. [-@fig:006])

![Меняем атрибуты](image/6.PNG){#fig:006 width=70%}

Так же попробуем выполнить разные дейтсвия с файлом, чтобы понять для чего нужен этот атрибут. (рис. [-@fig:007])

![Ни одна команда, меняющая файл не проходит, значит атрибут i указывает на то, что файл неизменяемый](image/7.PNG){#fig:007 width=70%}

# Выводы

Получили практических навыков работы в консоли с расширенными атрибутами файлов.
