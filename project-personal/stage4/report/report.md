---
## Front matter
title: "Индивидуальный проект"
subtitle: "Этап 4. Использование Nikto"
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

Исспользовать Nikto для поиска уязвимостей в системе.

# Теоретеческое введение

Nikto — веб-сканер, проверяющий веб-серверы на самые частые ошибки, возникающие обычно из-за человеческого фактора. 
Проверяет целевой веб-сервер на наличие опасных файлов и исполняемых сценариев, инструментов администрирования базами данных, устаревшего программного обеспечения. [@wiki:bash]

# Выполнение лабораторной работы

Посмотрим список опций для команды nikto. (рис. [-@fig:001])

![Опции для команды nikto](image/1.PNG){#fig:001 width=70%}

Запустим nikto для поиска уязвиомстей в системе. (рис. [-@fig:002])

![Нашли несколько уязвимостей, например, Sage 1.0b3](image/2.PNG){#fig:002 width=70%}

Проверим apache2 на уязвимости. (рис. [-@fig:003])

![Здесь также нашли несколько уязвимостей, например, несколько backdoor file manager](image/3.PNG){#fig:003 width=70%}

Проверим DVWA на уязвимости. (рис. [-@fig:004])

![Также нашли уязвимости и в DVWA, те же backdoor file manager](image/4.PNG){#fig:004 width=70%}

# Выводы

Использовали nikto для поиска уязвимостей в системе и приложениях.

# Список литературы{.unnumbered}

::: {#refs}
:::