---
## Front matter
title: "Индивидуальный проект"
subtitle: "Этап 3. Использование Hydra"
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

Применить метод bruteforce с помощью Hydra для подбора логина и пароля для слабозащищенных учетных записей.

# Теоретеческое введение

DVWA (Damn Vulnerable Web Application) - это веб-приложение на PHP/MySQL, которое "чертовски" уязвимо. 
Его основная цель — помочь специалистам по безопасности протестировать свои навыки и инструменты в легальной среде, помочь веб-разработчикам лучше понять процессы обеспечения безопасности веб-приложений, а также помочь студентам и преподавателям изучить вопросы безопасности веб-приложений в контролируемой учебной среде. 
Цель DVWA — отработать некоторые из наиболее распространенных веб-уязвимостей с различными уровнями сложности, используя простой и понятный интерфейс. 
Пожалуйста, обратите внимание, что в этом программном обеспечении есть как задокументированные, так и незадокументированные уязвимости. Это сделано намеренно. Вам предлагается попытаться обнаружить как можно больше проблем. [@github:bash]

Некоторые из уязвимостей веб приложений, который содержит DVWA:
Брутфорс: Брутфорс HTTP формы страницы входа - используется для тестирования инструментов по атаке на пароль методом грубой силы и показывает небезопасность слабых паролей.
Исполнение (внедрение) команд: Выполнение команд уровня операционной системы.
Межсайтовая подделка запроса (CSRF): Позволяет «атакующему» изменить пароль администратора приложений.
Внедрение (инклуд) файлов: Позволяет «атакующему» присоединить удалённые/локальные файлы в веб приложение.
SQL внедрение: Позволяет «атакующему» внедрить SQL выражения в HTTP из поля ввода, DVWA включает слепое и основанное на ошибке SQL внедрение.
Небезопасная выгрузка файлов: Позволяет «атакующему» выгрузить вредоносные файлы на веб сервер.
Межсайтовый скриптинг (XSS): «Атакующий» может внедрить свои скрипты в веб приложение/базу данных. DVWA включает отражённую и хранимую XSS.
Пасхальные яйца: раскрытие полных путей, обход аутентификации и некоторые другие.
DVWA имеет три уровня безопасности, они меняют уровень безопасности каждого веб приложения в DVWA:
Невозможный — этот уровень должен быть безопасным от всех уязвимостей. Он используется для сравнения уязвимого исходного кода с безопасным исходным кодом.
Высокий — это расширение среднего уровня сложности, со смесью более сложных или альтернативных плохих практик в попытке обезопасить код. Уязвимости не позволяют такой простор эксплуатации как на других уровнях.
Средний — этот уровень безопасности предназначен главным образом для того, чтобы дать пользователю пример плохих практик безопасности, где разработчик попытался сделать приложение безопасным, но потерпел неудачу.
Низкий — этот уровень безопасности совершенно уязвим и совсем не имеет защиты. Его предназначение быть примером среди уязвимых веб приложений, примером плохих практик программирования и служить платформой обучения базовым техникам эксплуатации. [@tuis:bash]

# Выполнение лабораторной работы

Сменили уровень безопасности на Low. (рис. [-@fig:001])

![Security level Low](image/1.PNG){#fig:001 width=70%}

Распаковали архив с файлом с наиболее распространенными паролями. (рис. [-@fig:002])

![Файл с паролями rockyou.txt](image/2.PNG){#fig:002 width=70%}

Зашли в раздел brute force. (рис. [-@fig:003])

![Окно с логином и паролем](image/3.PNG){#fig:003 width=70%}

Посмотрим код этой страницы. (рис. [-@fig:004])

![Запрос GET](image/4.PNG){#fig:004 width=70%}

Посмотрим содержимое файла. (рис. [-@fig:005])

![Содержимое файла config.inc.php.dist](image/5.PNG){#fig:005 width=70%}

Найдем в куки PHPSESSID. (рис. [-@fig:006])

![PHPSESSID домена 127.0.0.1](image/6.PNG){#fig:006 width=70%}

Запустим командой подбор паролей. (рис. [-@fig:007])

![Получили пароль password для логина admin, все получилось](image/7.PNG){#fig:007 width=70%}

Теперь создадим файл с частыми логинами и будем подбирать и логин и пароль. (рис. [-@fig:008])

![Получили две пары логинов и паролей, потому что для логина регистр не учитывается, а в файле это разные строки](image/8.PNG){#fig:008 width=70%}

# Выводы

Использовали Hydra и подобрали логин и пароль для слабозащищенной учетной записи.

# Список литературы{.unnumbered}

::: {#refs}
:::