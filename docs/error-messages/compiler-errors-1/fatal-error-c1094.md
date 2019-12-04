---
title: Неустранимая ошибка C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: 99bfeea47ff46b6dadac9b32fa61306d54520d0f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747401"
---
# <a name="fatal-error-c1094"></a>Неустранимая ошибка C1094

"-Zmval1": параметр командной строки не согласуется со значением, используемым для сборки предкомпилированного заголовка ("-Zmval2")

Значение, передаваемое в параметре [/Yc](../../build/reference/yc-create-precompiled-header-file.md) , должно иметь то же значение, которое передается в [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (значения **/ZM** должны быть одинаковыми во всех компиляциях, использующих или создающих один и тот же предкомпилированный заголовочный файл).

Следующий пример приводит к возникновению ошибки C1094:

```
// C1094.h
int func1();
```

Затем:

```cpp
// C1094.cpp
// compile with: /Yc"C1094.h" /Zm200
int u;
int main() {
   int sd = 32;
}
#include "C1094.h"
```

Затем:

```cpp
// C1094b.cpp
// compile with: /Yu"C1094.h" /Zm300 /c
#include "C1094.h"   // C1094 compile with /Zm200
void Test() {}
```
