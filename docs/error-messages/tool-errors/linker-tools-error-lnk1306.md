---
title: Ошибка средств компоновщика LNK1306 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1306
dev_langs:
- C++
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cc007a4a594c8593d7820365377f1c811b1e23c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050571"
---
# <a name="linker-tools-error-lnk1306"></a>Ошибка средств компоновщика LNK1306

> Функция точки входа библиотеки DLL не может быть управляемой; компиляция в машинный код

`DllMain` не удается скомпилировать в MSIL-код; она должна быть скомпилирована в машинный код.

Чтобы устранить эту проблему,

- Скомпилируйте файл, содержащий точку входа без **/CLR**.

- Поместите точку входа `#pragma unmanaged` разделе.

Дополнительные сведения:

- [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)

- [managed, unmanaged](../../preprocessor/managed-unmanaged.md)

- [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md)

- [Библиотеки DLL и поведение библиотеки времени выполнения Visual C++](../../build/run-time-library-behavior.md)

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK1306.

```cpp
// LNK1306.cpp
// compile with: /clr /link /dll /entry:NewDllMain
// LNK1306 error expected
#include <windows.h>
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
```

Чтобы устранить эту проблему, не используйте параметр/CLR скомпилируйте этот файл, или использовать `#pragma` директива размещение определения точки записи в неуправляемой разделов, как показано в следующем примере:

```cpp
// LNK1306fix.cpp
// compile with: /clr /link /dll /entry:NewDllMain
#include <windows.h>
#pragma managed(push, off)
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
#pragma managed(pop)
```
