---
title: Календарь событий
description: Бесплатная библиотека для работы с календарными событиями.
---

# Календарь событий

Автор: [Волков Александр](https://github.com/avolkov-git)

Лицензия: MIT License

## Описание

Реализация библиотеки компонента Календарь на нативном 1С: Элемент
Компонент содержит только календарь, без бизнес-логики (события, задачи и пр.), для того, чтобы Вы могли с легкостью интегрировать его в свой проект

Демонстрационное приложение [расположено тут](https://calendar.1cmycloud.com/applications/calendar-demo)

В демонстрационном приложении есть возмоность посмотреть оба варианта дизайна

**Звезды, форки и помощь в доработке приветствуются**

## Возможности

**На данный момент:**
- Календарь с построением матрицы на основе массива данных (дни месяца)
- Переключение по между месяцами кнопками "Вперед / Назад"
- Два варианта дизайна: плоский, в карточках
- Мобильная адаптация через свойство компонента
- В ветке разработки реализован компонент "СобытияПланировщика"

**В планах:**
- Реализация механизма управления цветом карточек/кнопок
- Форма выбора месяца/года
- АПИ для бизнес-логики
- Компонент отображения данных бизнес-логики
- Возможность установки фотографии вместо фона элемента календаря (по аналогии с Telegram)

## Использование

```YAML
-
    Тип: Календарь
    Имя: Календарь
    ВариантДизайна: =ВариантДизайнаКалендаря.Плоский 
    МобильныйВариант: Ложь

```

**ВариантДизайна: Перечисление.ВариантДизайнаКалендаря** (по-умолчанию: Плоский)

Доступные значения
 * ВариантДизайнаКалендаря.Плоский
 * ВариантДизайнаКалендаря.Карточки

**МобильныйВариант: Булево** (по-умолчанию: Ложь)
 * можете передать результат вызова собственной функции опеределния вида клиенте/устройства

## Скачать

[Репозиторий на Gitflic.ru](https://gitflic.ru/project/enterprise_element_community/calendar)

[Прямая ссылка на скачивание версии 1.0.1.xlib - Совместимость 9.0 - 04.06.2025](https://gitflic.ru/project/enterprise_element_community/calendar/release/82e9a083-3789-4ecf-8275-eb53fc304b35/9232bd3e-ea48-4708-ab6e-3bb0395c18f3/download)   

## Лицензия

MIT License

Copyright (c) 2025 Alexandr Volkov

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
