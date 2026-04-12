---
title: ОКМС
description: Общероссийский классификатор стран мира
---

# Общероссийский классификатор стран мира

Автор: [Волков Александр](https://github.com/avolkov-git)

Лицензия: MIT License

## Описание

Реализация библиотеки "Страны мира (Общероссийский классификатор стран мира) на нативном 1С: Элемент

**Звезды, форки и помощь в доработке приветствуются**

## Возможности

**На данный момент:**
- Справочник СтраныМира
- Загрузка данных из макета JSON с сайта [Портал открытых данных правительства Москвы](https://data.mos.ru/opendata/2724) 
- Флаги всех стран (svg) по классификатору
- Форма объекта СтраныМира
- Форма списка СтраныМира (с отметками уже загруженных стран)
- Основные коды классификатора (GlobalID, ALF2, ALF3)

**Начиная с версии 1.0.5:**
- Страна по-умолчанию

**В планах:**
- Загрузка данных через API, с ИТС, из выбранного файла
- Телефонный код страны (+7, +103 и т.д.)
- Маска телефонного номера

## Использование:

В библиотеке присутствует справочник “СтраныМира”, который можно добавлять в качестве свойства в собственных объектах метаданных. Например справочник “СтраныМира” используется как реквизит справочника “Банки”. Пример yaml файла подключения ниже

```YAML
ВидЭлемента: Справочник
Ид: 69cd7992-d93e-4561-93dd-208eaf13bc5d
Имя: Банки
ОбластьВидимости: Глобально
Импорт:
    - alexandrvolkov::ОКСМ::ПользовательскийИнтерфейс
Реквизиты:
    - 
        Имя: Наименование
    - 
        Ид: 9e4676ed-5eaa-47cb-a4e4-158882d3c947
        Имя: Страна
        Тип: Страны.Ссылка?
```

Для работа со списком справочника в интерфейсе доступна форма **СтраныМираФормаСписка**, тип которой можно использовать в качестве параметра **ТипФормы** компоненты **НавигационнаяКоманда**. Пример использования ниже:

```YAML
ВидЭлемента: НавигационнаяКоманда
Ид: 8d82db59-b2d1-4364-9ce0-8f0479e6de68
Имя: Страны
Импорт:
    - alexandrvolkov::ОКСМ::ПользовательскийИнтерфейс
ОбластьВидимости: ВПодсистеме
Представление: Страны
ТипФормы: alexandrvolkov::ОКСМ::ПользовательскийИнтерфейс::СтраныФормаСписка
```

Пример использования компонента выбора страны по-умолчанию

```YAML
-
    Тип: СтранаПоУмолчаниюКомпонент
    Имя: СтранаПоУмолчаниюКомпонент
    ОтображатьИзображениеФлага: Истина 
    ЗаголовокКомпонентаВвода: "Укажите основную страну"

```

## Изменения в версиях:
***
### Release 1.0.5

 - Страна по-умолчанию. Добавлена возможность указывать страну по-умолчанию. Реализован программный интерфейс для управления этим параметром: `ОКМС.СтранаПоУмолчанию()`, `ОКМС.УстановитьСтрануПоУмолчанию()`

 - Добавлен контракт сервиса `"ПереопределениеПрограммногоИнтерфейса"`, с возможностью переопеределить/расширить методы программного интерфейса: `ОКМС.СтранаПоУмолчаниюАльфа3()`, `ОКМС.СтранаПоУмолчанию()`

### Release 1.0.5.3

Добавлен компонент `СтранаПоУмолчаниюКомпонент`, позволяющий изменить значение константы "Страна по-умолчанию" в пользовательском режиме

**Доступные свойства**
 * ОтображатьИзображениеФлага: Булево - отображать иконку флага в поле ввода. По-умолчанию = Ложь
 * ИзображенияКнопкиЗаписать: ДвоичныйОбъект.Ссылка? - позволяет заменить изображение кнопки "Записать". По-умолчанию = Сохранить.svg
 * ЗаголовокКомпонентаВвода: Строка? - произвольный заголовок поля ввода. По-умолчанию = "Текущая страна"

 ## Скачать

[Репозиторий на Gitflic.ru](https://gitflic.ru/project/enterprise_element_community/country-lib)

[Прямая ссылка на скачивание версии 1.0.5.xlib - Совместимость 8.0](https://gitflic.ru/project/enterprise_element_community/country-lib/release/119470a2-7e10-42d1-ac9e-cd1a7016c164/e64f6287-203e-4b9b-8482-f7f71528e283/download)

[Прямая ссылка на скачивание версии 1.0.5.3.xlib - Совместимость 9.0](https://gitflic.ru/project/enterprise_element_community/country-lib/release/9d0be8e5-f2a6-4dda-ad4e-89b0b1d81093/c16aca8d-f381-4521-a957-c5bea70b6198/download)

## Лицензия

MIT License

Copyright (c) 2025 Alexandr Volkov, Atrem Sobolevsky

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