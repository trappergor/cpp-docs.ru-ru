---
title: Ошибка компилятора C2004
ms.date: 11/04/2016
f1_keywords:
- C2004
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
ms.openlocfilehash: c4f099ba241b56291074202e6c03ad98ee97f756
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743507"
---
# <a name="compiler-error-c2004"></a>Ошибка компилятора C2004

требуется "defined(id)"

Идентификатор должен быть заключен в круглые скобки после ключевого слова препроцессора.

Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: отсутствуют круглые скобки в директиве препроцессора. Если в директиве препроцессора отсутствует закрывающая круглая скобка, компилятор выдаст сообщение об ошибке.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2004:

```cpp
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

Возможное решение:

```cpp
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
