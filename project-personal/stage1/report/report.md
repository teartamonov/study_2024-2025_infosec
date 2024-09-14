---
## Front matter
title: "Индивидуальный проект"
subtitle: "Этап 1. Установка Kali Linux"
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

Установить Kali Linux на виртуальную машину для дальнейшей работы.

# Выполнение лабораторной работы

Зашли на официальный сайт Kali Linux и нашли pre-build virtual machines [@wiki:bash]. (рис. [-@fig:001])

![Список доступных для загрузки образов](image/1.PNG){#fig:001 width=70%}

Открыли VirtualBox и добавили образ. Наша система уже установлена и настроена, добавили в настройках монитор и еще одно ядро процессора. (рис. [-@fig:002])

![Параметры предустановленной системы](image/2.PNG){#fig:002 width=70%}

Запустили систему. (рис. [-@fig:003])

![Окно входа в систему](image/3.PNG){#fig:003 width=70%}

Успешно вошли, поменяли имя и пароль пользователя. (рис. [-@fig:004])

![Окно изменения имени пользователя](image/4.PNG){#fig:004 width=70%}

# Выводы

Успешно установили дистрибутив Kali Linux для дальнейшей работы.

# Список литературы{.unnumbered}

::: {#refs}
:::