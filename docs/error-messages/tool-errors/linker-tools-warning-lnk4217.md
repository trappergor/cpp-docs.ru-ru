---
title: Предупреждение средств компоновщика LNK4217
ms.date: 11/04/2016
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: 12766241832d39f0b47ed85036c0ebeb0447fc75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448052"
---
# <a name="linker-tools-warning-lnk4217"></a>Предупреждение средств компоновщика LNK4217

локально определенный символ «символ» импортируется в функции «функция»

[__declspec(dllimport)](../../cpp/dllexport-dllimport.md) был указан для символа, несмотря на то, что этот символ определен локально. Удалить `__declspec` модификатор, чтобы устранить это предупреждение.

`symbol` — Это имя символа, который определен в образе. `function` — функция, которая импортирует символ.

Это предупреждение не будет отображаться при компиляции с помощью параметра [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).

LNK4217 также может возникать при попытке связать два модуля, когда следует компилировать второй модуль с библиотекой импорта первого модуля.

```
// LNK4217.cpp
// compile with: /LD
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

Затем:

```
// LNK4217b.cpp
// compile with: /c
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

При попытке связать эти два модуля приведет к LNK4217, компиляции во втором примере с библиотекой импорта первого образца для решения.