---
title: Предупреждение средств компоновщика LNK4217
ms.date: 04/15/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: f1ea3cd0a8770571ae5c55d29a901c134311550f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410230"
---
# <a name="linker-tools-warning-lnk4217"></a>Предупреждение средств компоновщика LNK4217

> символ "*символ*«определен в»*filename_1.obj*«импортируется путем»*filename_2.obj*«в функции»*функция*"

[__declspec(dllimport)](../../cpp/dllexport-dllimport.md) был указан для символа, несмотря на то, что этот символ определен в объектный файл в тот же образ. Удалить `__declspec(dllimport)` модификатор, чтобы устранить это предупреждение.

## <a name="remarks"></a>Примечания

*символ* является имя символа, который определен в образе. *функция* — функция, которая импортирует символ.

Это предупреждение не отображается при компиляции с помощью [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) параметр.

LNK4217 также может возникать при попытке связать два модуля, когда следует компилировать второй модуль с библиотекой импорта первого модуля.

```cpp
// LNK4217.cpp
// compile with: /LD
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

Затем:

```cpp
// LNK4217b.cpp
// compile with: /c
#include "windows.h"
__declspec(dllexport) void func(unsigned short*) {}
```

При попытке связать эти два модуля приведет к LNK4217. Скомпилируйте второй образец с библиотекой импорта первого образца для решения.

## <a name="see-also"></a>См. также

[Предупреждение средств компоновщика LNK4049](linker-tools-warning-lnk4049.md) \
[Предупреждение LNK4286 средств компоновщика](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)