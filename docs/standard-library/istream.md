---
title: '&lt;istream&gt;'
ms.date: 11/04/2016
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
ms.openlocfilehash: 8e9675a673462c8eaab94d29a3ae36a4786737b7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687854"
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

Определяет шаблон класса basic_istream, который устраняет извлечения для iostream и шаблон класса basic_iostream, который исправляет как вставки, так и извлечения. Заголовок также определяет связанный манипулятор. Этот файл заголовок обычно автоматически включается другим заголовком iostreams, его редко приходится включать напрямую.

## <a name="syntax"></a>Синтаксис

```cpp
#include <istream>
```

### <a name="typedefs"></a>Typedefs

|Имя типа|Описание|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|Тип, `basic_iostream` специализированный для **char**.|
|[istream](../standard-library/istream-typedefs.md#istream)|Тип, `basic_istream` специализированный для **char**.|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|Тип `basic_iostream`, специализированный для **wchar**.|
|[wistream](../standard-library/istream-typedefs.md#wistream)|Тип `basic_istream`, специализированный для **wchar**.|

### <a name="manipulators"></a>Манипуляторы

|||
|-|-|
|[ws](../standard-library/istream-functions.md#ws)|Пропускает пробелы в потоке.|
|[swap](../standard-library/istream-functions.md#istream_swap)|Меняет местами два объекта потоков.|

### <a name="operators"></a>Операторы

|оператора|Описание|
|-|-|
|[оператор>>](../standard-library/istream-operators.md#op_gt_gt)|Извлекает символы и строки из потока.|

### <a name="classes"></a>Классы

|Class|Описание|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|Класс потока, поддерживающий ввод и вывод.|
|[basic_istream](../standard-library/basic-istream-class.md)|Шаблон класса описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока с элементами типа `Elem`, которые также называются [char_type](../standard-library/basic-ios-class.md#char_type), признаки символов которых определяются классом `Tr`, также известным как [ traits_type](../standard-library/basic-ios-class.md#traits_type).|

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
