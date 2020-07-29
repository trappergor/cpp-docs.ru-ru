---
title: Аргументы функции ссылочного типа
ms.date: 08/27/2018
helpviewer_keywords:
- arguments [C++], function
- functions [C++], parameters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
ms.openlocfilehash: 5a409efbe2908954d394656cb989ad6b80a9ce22
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233643"
---
# <a name="reference-type-function-arguments"></a>Аргументы функции ссылочного типа

Вместо крупных объектов эффективнее бывает передавать функциям ссылки. Это позволяет компилятору передавать адрес объекта, сохраняя при этом синтаксис, который использовался бы для обращения к этому объекту. Рассмотрим следующий пример, в котором используется структура `Date`:

```cpp
// reference_type_function_arguments.cpp
#include <iostream>

struct Date
{
    short Month;
    short Day;
    short Year;
};

// Create a date of the form DDDYYYY (day of year, year)
// from a Date.
long DateOfYear( Date& date )
{
    static int cDaysInMonth[] = {
        31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31
    };
    long dateOfYear = 0;

    // Add in days for months already elapsed.
    for ( int i = 0; i < date.Month - 1; ++i )
        dateOfYear += cDaysInMonth[i];

    // Add in days for this month.
    dateOfYear += date.Day;

    // Check for leap year.
    if ( date.Month > 2 &&
        (( date.Year % 100 != 0 || date.Year % 400 == 0 ) &&
        date.Year % 4 == 0 ))
        dateOfYear++;

    // Add in year.
    dateOfYear *= 10000;
    dateOfYear += date.Year;

    return dateOfYear;
}

int main()
{
    Date date{ 8, 27, 2018 };
    long dateOfYear = DateOfYear(date);
    std::cout << dateOfYear << std::endl;
}
```

Приведенный выше код показывает, что доступ к членам структуры, передаваемым по ссылке, осуществляется с помощью оператора выбора члена (**.**), а не оператора выделения члена указателя ( **->** ).

Хотя аргументы, передаваемые как ссылочные типы, определяют синтаксис типов, не являющихся указателями, они поддерживают одну важную характеристику типов указателей: они являются изменяемыми, если не объявлены как **`const`** . Поскольку задача приведенного выше кода заключается не в том, чтобы изменить объект `date`, более подходящим будет следующий прототип функции:

```cpp
long DateOfYear( const Date& date );
```

Этот прототип гарантирует, что функция `DateOfYear` не изменит его аргумент.

Любая функция, заданная как принимающая ссылочный тип, может принять объект того же типа в своем месте, так как существует стандартное преобразование из *TypeName* в *TypeName* <strong>&</strong> .

## <a name="see-also"></a>См. также статью

[Справочные материалы](../cpp/references-cpp.md)<br/>
