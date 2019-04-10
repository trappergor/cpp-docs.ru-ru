---
title: Предупреждение средств компоновщика LNK4217
ms.date: 04/09/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: 3fcb806afa064a4f6d9c9c0680c617662a3b9a21
ms.sourcegitcommit: 0ad3f4517e64900a2702dd3d366586f9e2bce2c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2019
ms.locfileid: "59477396"
---
# <a name="linker-tools-warning-lnk4217"></a>Предупреждение средств компоновщика LNK4217

> символ "*символ*«определен в»*filename_1.obj*«импортируется путем»*filename_2.obj*«в функции»*функция*"

[__declspec(dllimport)](../../cpp/dllexport-dllimport.md) был указан для символа, несмотря на то, что этот символ определен в объектный файл в тот же образ. Удалить `__declspec(dllimport)` модификатор, чтобы устранить это предупреждение.

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