---
title: Предупреждение компилятора (уровень 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: ecaabd482049771b1d3915470a2be7a52e36d361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462391"
---
# <a name="compiler-warning-level-1-c4747"></a>Предупреждение компилятора (уровень 1) C4747

Вызов управляемого «entrypoint»: управляемый код может не выполняться во время блокировки загрузчика, точки входа библиотеки DLL и поступившим из них вызовам

Компилятор обнаружил (возможно) точка входа библиотеки DLL, скомпилированные в MSIL.  Из-за потенциальных проблем при загрузке библиотеки DLL, точка входа была скомпилирована в MSIL рекомендуется компилировать функцию точки входа DLL в MSIL.

Дополнительные сведения см. в разделе [Инициализация смешанных сборок](../../dotnet/initialization-of-mixed-assemblies.md) и [Ошибка средств компоновщика LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не компилировать модуль с помощью **/CLR**.

1. Пометьте функцию точки входа с `#pragma unmanaged`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4747.

```
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