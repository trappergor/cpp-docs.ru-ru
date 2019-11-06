---
title: Предупреждение компилятора (уровень 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 13c56c2261cd069e7edec63921c198e2bee56c95
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626696"
---
# <a name="compiler-warning-level-1-c4272"></a>Предупреждение компилятора (уровень 1) C4272

"функция": помечен как __declspec (dllimport); При импорте функции необходимо указать собственное соглашение о вызовах.

Экспорт функции, помеченной соглашением о вызовах [__clrcall](../../cpp/clrcall.md) , является ошибкой, и компилятор выдает это предупреждение при попытке импортировать функцию, помеченную `__clrcall`.

Следующий пример приводит к возникновению ошибки C4272:

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```