---
title: Оператор NULL
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
ms.openlocfilehash: 2797937b184bebe0e29f8e5eae428f601c824811
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480695"
---
# <a name="null-statement"></a>Оператор NULL

«Оператор null» — это инструкция выражения с *выражение* отсутствует. Она полезна, если синтаксис языка требует инструкции, но не оценки выражения. Она состоит из точки с запятой.

Инструкции null часто используются как местозаполнители в инструкциях итерации или как инструкции, в которых нужно разместить метки в конце сложных инструкций или функций.

В следующем фрагменте кода показано, как копировать одну строку в другую. Кроме того, код содержит инструкцию null.

```cpp
// null_statement.cpp
char *myStrCpy( char *Dest, const char *Source )
{
    char *DestStart = Dest;

    // Assign value pointed to by Source to
    // Dest until the end-of-string 0 is
    // encountered.
    while( *Dest++ = *Source++ )
        ;   // Null statement.

    return DestStart;
}

int main()
{
}
```

## <a name="see-also"></a>См. также

[Оператор выражений](../cpp/expression-statement.md)