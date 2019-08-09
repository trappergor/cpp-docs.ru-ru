---
title: '&lt;ostream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
ms.openlocfilehash: 8de66718dab10b5c95e8c1ab7fd0bd17e9b4ee5e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448170"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

Определяет класс шаблона [basic_ostream](../standard-library/basic-ostream-class.md), который является посредником при вставке для iostreams. Заголовок также определяет несколько связанных манипуляторов. (Этот заголовок обычно включается автоматически при использовании других заголовков iostream. Его редко приходится включать напрямую.)

## <a name="syntax"></a>Синтаксис

```cpp
#include <ostream>
```

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Создает тип из `basic_ostream` , который специализируется на **char** и `char_traits` специализированный для **типа char**.|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Создает тип из `basic_ostream` , специализированного для **wchar_t** и `char_traits` специализированного для **wchar_t**.|

### <a name="manipulators"></a>Манипуляторы

|||
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|Завершает строку и очищает буфер.|
|[ends](../standard-library/ostream-functions.md#ends)|Завершает строку.|
|[flush](../standard-library/ostream-functions.md#flush)|Очищает буфер.|
|[swap](../standard-library/ostream-functions.md#swap)|Меняет местами значения левого параметра объекта `basic_ostream` со значениями правого параметра объекта `basic_ostream`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор<<](../standard-library/ostream-operators.md#op_lt_lt)|Записывает в поток различные типы.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|Класс шаблона, который описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
