---
title: Предупреждение компилятора (уровень 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: 623b29d345a850cc312f23e4c521aa0be5b47242
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052441"
---
# <a name="compiler-warning-level-1-c4747"></a>Предупреждение компилятора (уровень 1) C4747

Вызов управляемой "EntryPoint": управляемый код не может выполняться при блокировке загрузчика, включая точку входа DLL и вызовы, достигнутые в точке входа DLL

Компилятор обнаружил (возможно) точку входа DLL, скомпилированную в MSIL.  Из-за потенциальных проблем при загрузке библиотеки DLL, точка входа которой была скомпилирована в MSIL, настоятельно не рекомендуется компилировать функцию точки входа DLL в MSIL.

Дополнительные сведения см. в разделе [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md) и [средств компоновщика ошибка LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не компилируйте модуль с помощью **параметра/clr**.

1. Пометьте функцию точки входа `#pragma unmanaged`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4747.

```cpp
// C4747.cpp
// compile with: /clr /c /W1
// C4747 expected
#include <windows.h>

// Uncomment the following line to resolve.
// #pragma unmanaged

BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {
   return TRUE;
};
```