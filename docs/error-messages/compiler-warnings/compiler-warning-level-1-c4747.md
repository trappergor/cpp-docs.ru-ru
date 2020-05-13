---
title: Предупреждение компилятора (уровень 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: 2fd7f0960966a981d82d19e7b2533b1ffcd3bc00
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175198"
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
