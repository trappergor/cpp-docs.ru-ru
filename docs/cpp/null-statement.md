---
title: Оператор NULL
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
ms.openlocfilehash: 167a1e579c15fd59da1979efd9aa979184318115
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177811"
---
# <a name="null-statement"></a>Оператор NULL

Оператор null является оператором выражения с отсутствующим *выражением* . Она полезна, если синтаксис языка требует инструкции, но не оценки выражения. Она состоит из точки с запятой.

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

## <a name="see-also"></a>См. также раздел

[Оператор выражений](../cpp/expression-statement.md)
