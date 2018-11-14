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
ms.openlocfilehash: eb73c77f0e2658cf750cf17ca85549a09d1cbe51
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523771"
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
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Создает тип из `basic_ostream` который специализируется на **char** и `char_traits` специализированный на **char**.|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Создает тип из `basic_ostream` который специализируется на **wchar_t** и `char_traits` специализированный на **wchar_t**.|

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

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
