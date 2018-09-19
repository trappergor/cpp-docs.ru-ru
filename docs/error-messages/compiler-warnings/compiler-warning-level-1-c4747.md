---
title: Предупреждение компилятора (уровень 1) C4747 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4747
dev_langs:
- C++
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d3eb5b83fedc7455cbf1b97119296a6eb6a1ab1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118483"
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