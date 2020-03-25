---
title: Предупреждение компилятора (уровень 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 747b9e60ad2b8b0036c6eac50d44c2d70277384f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163111"
---
# <a name="compiler-warning-level-1-c4272"></a>Предупреждение компилятора (уровень 1) C4272

"функция": помечена как __declspec (dllimport); При импорте функции необходимо указать собственное соглашение о вызовах.

Экспорт функции, помеченной соглашением о вызовах [__clrcall](../../cpp/clrcall.md) , является ошибкой, и компилятор выдает это предупреждение при попытке импортировать функцию, помеченную как `__clrcall`.

Следующий пример приводит к возникновению ошибки C4272:

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```
