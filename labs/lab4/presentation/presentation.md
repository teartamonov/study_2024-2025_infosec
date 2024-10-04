---
## Front matter
lang: ru-RU
title: Лабораторная работа № 4
subtitle: Дискреционное разграничение прав в Linux. Расширенные атрибуты
author:
  - Артамонов Т. Е.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 27 сентября 2024

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

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

## Теоретическое введение

chattr — команда, изменяющая атрибуты файлов на файловых системах ext2fs, ext3, ext4 и частично на других файловых системах Linux.
Операторы 
- "+" обозначает добавление указанных атрибутов к существующим
- "-" обозначает их снятие
- "=" обозначает установку только этих атрибутов файлам.

Символы "ASacDdijsu" указывают на новые атрибуты файлов.

# Выполнение лабораторной работы

## Попробуем добавить атрибут к файлу от имени записи guest. (рис. [-@fig:001])

![Получаем ошибку, поэтому делаем это от имени администратора](image/1.PNG){#fig:001 width=70%}

## Посмотрим сработала ли команда. (рис. [-@fig:002])

![К файлу добавился атбрибут "a"](image/2.PNG){#fig:002 width=70%}

## Попробуем различные действия с этим файлом. (рис. [-@fig:003])

![Сработала только команда чтения](image/3.PNG){#fig:003 width=70%}

## Пробуем дальше. (рис. [-@fig:004])

![Несмотря на то, что владелец файла может читать и редактировать его по модификаторам доступа, мы не можем менять его как хотим](image/4.PNG){#fig:004 width=70%}

## Пробуем дальше. (рис. [-@fig:005])

![Сработала только команда дозаписи в файл, то есть файл открыт только для добавления информации в него](image/5.PNG){#fig:005 width=70%}

## Теперь снимем атрибут "a" и поставим "i". (рис. [-@fig:006])

![Меняем атрибуты](image/6.PNG){#fig:006 width=70%}

## Так же попробуем выполнить разные дейтсвия с файлом, чтобы понять для чего нужен этот атрибут. (рис. [-@fig:007])

![Ни одна команда, меняющая файл не проходит, значит атрибут i указывает на то, что файл неизменяемый](image/7.PNG){#fig:007 width=70%}

## Выводы

Получили практических навыков работы в консоли с расширенными атрибутами файлов.

## Список литературы

1. chattr [Электронный ресурс]. Wikimedia Foundation, Inc., 2024. URL: https://en.wikipedia.org/wiki/Chattr.