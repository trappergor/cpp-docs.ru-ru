---
title: Ключевое слово SECTIONS (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: d70c8d6e7188844a8721b37d5e80fb88a4e21ef9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412800"
---
# <a name="sections-cc"></a>Ключевое слово SECTIONS (C/C++)

Представляет раздел из одного или нескольких `definitions` , которые описатели доступа для разделов выходного файла проекта.

```
SECTIONS
definitions
```

## <a name="remarks"></a>Примечания

Каждое определение должно находиться в отдельной строке. `SECTIONS` Ключевое слово может находиться на той же строке, что первое определение, или на предыдущей строке. DEF-файл может содержать один или несколько `SECTIONS` инструкций.

Это `SECTIONS` инструкция задает атрибуты для одного или нескольких разделов в файле образа и может использоваться для переопределения атрибуты по умолчанию для каждого типа раздела.

Формат `definitions` является:

`.section_name specifier`

где `.section_name` — это имя раздела в образе программы и `specifier` равно одному или нескольким из следующих модификаторов доступа:

|Модификатор|Описание:|
|--------------|-----------------|
|`EXECUTE`|Раздел является исполняемого файла|
|`READ`|Позволяет выполнять операции чтения данных|
|`SHARED`|Секция всем процессам, загружающим образ|
|`WRITE`|Позволяет выполнять операции записи данных|

Разделяйте имена описатель с пробелом. Пример:

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` Помечает начало список разделе `definitions`. Каждый `definition` должны находиться в отдельной строке. `SECTIONS` Ключевое слово может быть в той же строке, что и первый `definition` или на предыдущей строке. DEF-файл может содержать один или несколько `SECTIONS` инструкций. `SEGMENTS` Ключевое слово поддерживается как синоним для `SECTIONS`.

Поддерживается в более ранних версиях Visual C++:

```
section [CLASS 'classname'] specifier
```

`CLASS` Ключевое слово поддерживается для совместимости, но учитывается.

Эквивалентный способ указание атрибутов раздела — с помощью [/SECTION](../../build/reference/section-specify-section-attributes.md) параметр.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)
