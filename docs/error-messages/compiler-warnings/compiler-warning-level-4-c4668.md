---
title: Предупреждение компилятора (уровень 4) C4668
ms.date: 11/04/2016
f1_keywords:
- C4668
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
ms.openlocfilehash: 11d96941a1efddde87068af8829e24259f2fa312
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408164"
---
# <a name="compiler-warning-level-4-c4668"></a>Предупреждение компилятора (уровень 4) C4668

"символ" не определен в качестве макроса препроцессора и будет заменен в "директивах" на "0"

Символ, который не был определен использовался в директиве препроцессора. Символ будет вычислять по false. Чтобы определить символ, можно использовать либо [#define директива](../../preprocessor/hash-define-directive-c-cpp.md) или [/D](../../build/reference/d-preprocessor-definitions.md) параметр компилятора.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4668:

```
// C4668.cpp
// compile with: /W4
#include <stdio.h>

#pragma warning (default : 4668)   // turn warning on

int main()
{
    #if q   // C4668, q is not defined
        printf_s("defined");
    #else
        printf_s("undefined");
    #endif
}
```