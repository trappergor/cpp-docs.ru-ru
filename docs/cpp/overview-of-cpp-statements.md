---
title: Общие сведения об операторах в C++
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
ms.openlocfilehash: 9493860087331ee2d8ff05a5c0bd59c7a46ad51a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676555"
---
# <a name="overview-of-c-statements"></a>Общие сведения об операторах в C++

Операторы C++ выполняются последовательно, кроме случаев, когда эта последовательность специально изменяется с помощью оператора выражения, оператора выбора, оператора итерации или оператора перехода.

Операторы могут быть следующих типов:

```
labeled-statement
expression-statement
compound-statement
selection-statement
iteration-statement
jump-statement
declaration-statement
try-throw-catch
```

В большинстве случаев синтаксис инструкции при этом C++ идентична ANSI C. Основное различие между ними заключается, в C, объявления разрешены только в начале блока; Добавляет C++ *оператор объявления*, который эффективно снимает данное ограничение. Это позволяет вводить переменные в том месте программы, в котором можно вычислить заранее рассчитанное значение инициализации.

Объявление переменных внутри блоков также обеспечивает точный контроль над областью видимости и временем существования этих переменных.

В разделах, посвященных операторам, рассматриваются следующие ключевые слова языка C++:

|||||
|-|-|-|-|
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||

## <a name="see-also"></a>См. также

[Операторы](../cpp/statements-cpp.md)