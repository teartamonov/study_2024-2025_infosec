---
## Front matter
lang: ru-RU
title: Индивидуальный проект
subtitle: Этап 1. Установка Kali Linux
author:
  - Артамонов Т. Е.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 14 сентября 2024

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Артамонов Тимофей Евгеньевич
  * студент группы НКНбд-01-21
  * Российский университет дружбы народов
  * <https://github.com/teartamonov>

:::
::: {.column width="30%"}

![](image/ava.jpg)

:::
::::::::::::::


## Цель работы

Установить Kali Linux на виртуальную машину для дальнейшей работы.

# Выполнение лабораторной работы

## Зашли на официальный сайт Kali Linux и нашли pre-build virtual machines. (рис. [-@fig:001])

![Список доступных для загрузки образов](image/1.PNG){#fig:001 width=70%}

## Открыли VirtualBox и добавили образ. Наша система уже установлена и настроена, добавили в настройках монитор и еще одно ядро процессора. (рис. [-@fig:002])

![Параметры предустановленной системы](image/2.PNG){#fig:002 width=70%}

## Запустили систему. (рис. [-@fig:003])

![Окно входа в систему](image/3.PNG){#fig:003 width=70%}

## Успешно вошли, поменяли имя и пароль пользователя. (рис. [-@fig:004])

![Окно изменения имени пользователя](image/4.PNG){#fig:004 width=70%}

## Выводы

Успешно установили дистрибутив Kali Linux для дальнейшей работы.

## Список литературы

1. Kali Linux virtual machines [Электронный ресурс]. Wikimedia Foundation, Inc., 2024. URL: https://www.kali.org/get-kali/#kali-virtual-machines.