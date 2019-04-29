---
title: Неустранимая ошибка C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: 23891a783a018f6d84ea820af98992f61632984c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366502"
---
# <a name="fatal-error-c1094"></a>Неустранимая ошибка C1094

"-Zmval1": параметр командной строки несовместим со значением, использованным для сборки предкомпилированного заголовка ("-Zmval2")

Значение, передаваемое [/Yc](../../build/reference/yc-create-precompiled-header-file.md) должно быть значение, передается [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (**/Zm** значения должны быть одинаковыми во всех компиляциях, использующих или его необходимо создать предварительно скомпилированные файл заголовка).

Следующий пример приводит к возникновению ошибки C1094:

```
// C1094.h
int func1();
```

Затем:

```
// C1094.cpp
// compile with: /Yc"C1094.h" /Zm200
int u;
int main() {
   int sd = 32;
}
#include "C1094.h"
```

Затем:

```
// C1094b.cpp
// compile with: /Yu"C1094.h" /Zm300 /c
#include "C1094.h"   // C1094 compile with /Zm200
void Test() {}
```