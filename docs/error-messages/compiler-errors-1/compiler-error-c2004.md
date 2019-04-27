---
title: Ошибка компилятора C2004
ms.date: 11/04/2016
f1_keywords:
- C2004
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
ms.openlocfilehash: fb100d977188cd3a7d5b0ebbb3e29b53942871dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208949"
---
# <a name="compiler-error-c2004"></a>Ошибка компилятора C2004

требуется "defined(id)"

Идентификатор должен быть заключен в круглые скобки после ключевого слова препроцессора.

Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: отсутствуют круглые скобки в директиве препроцессора. Если в директиве препроцессора отсутствует закрывающая круглая скобка, компилятор выдаст сообщение об ошибке.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2004:

```
// C2004.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG   // C2004
        printf_s("DEBUG defined\n");
    #endif
}
```

## <a name="example"></a>Пример

Возможное решение

```
// C2004b.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG)
        printf_s("DEBUG defined\n");
    #endif
}
```