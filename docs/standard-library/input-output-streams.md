---
title: Потоки ввода-вывода
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
ms.openlocfilehash: 54b53f96d487e466106fe92a01affa7bd3e55c16
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228262"
---
# <a name="inputoutput-streams"></a>Потоки ввода/вывода

`basic_iostream`, который определен в файле заголовка \<istream> , является шаблоном класса для объектов, обрабатывающих входные и выходные потоки ввода-вывода на основе символов.

Существуют два определения типов, которые определяют специализации для отдельных символов `basic_iostream` и могут облегчить чтение кода: `iostream` (не путать с файлом заголовка \<iostream> ) — это поток ввода-вывода, основанный на `basic_iostream<char>` `wiostream` . — это поток ввода-вывода, основанный на `basic_iostream<wchar_t>` .

Дополнительные сведения см. в разделах [Класс basic_iostream](../standard-library/basic-iostream-class.md), [iostream](../standard-library/basic-iostream-class.md) и [wiostream](../standard-library/basic-iostream-class.md).

Производным из `basic_iostream` является шаблон класса `basic_fstream`, который используется для потоковой передачи символьных данных в файлы и из них.

Также имеются определения типов, которые предоставляют специальные для символов специализации для `basic_fstream`. Они представляют собой `fstream` поток файлового ввода-вывода, основанный на **`char`** , и `wfstream` , который является потоком файлового ввода-вывода, основанным на **`wchar_t`** . Дополнительные сведения см. в разделах [Класс basic_fstream](../standard-library/basic-fstream-class.md), [fstream](../standard-library/basic-fstream-class.md) и [wfstream](../standard-library/basic-fstream-class.md). Использование этих определений типов требует включения файла заголовка \<fstream> .

> [!NOTE]
> Если объект `basic_fstream` используется для выполнения файлового ввода-вывода, хотя базовый буфер содержит отдельно назначенные позиции для чтения и записи, текущие позиции ввода и вывода связываются друг с другом, поэтому, чтение некоторых данных перемещает позицию вывода.

Шаблон класса `basic_stringstream` и его общая специализация `stringstream` часто используются для работы с объектами потока ввода-вывода для вставки и извлечения символьных данных. Дополнительные сведения см. в разделе [Класс basic_stringstream](../standard-library/basic-stringstream-class.md).

## <a name="see-also"></a>См. также статью

[StringStream](../standard-library/basic-stringstream-class.md)\
[Класс basic_stringstream](../standard-library/basic-stringstream-class.md)\
[\<sstream>](../standard-library/sstream.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)
