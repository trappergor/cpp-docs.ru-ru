---
title: Предупреждение компилятора (уровень 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 26e136aa395729d520f4a71a06b6dc212cf21f8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479996"
---
# <a name="compiler-warning-level-1-c4272"></a>Предупреждение компилятора (уровень 1) C4272

«функция»: помечается как __declspec(dllimport); При импорте функции необходимо указать собственное соглашение о вызове.

Является ошибкой экспортировать функцию, отмеченные [__clrcall](../../cpp/clrcall.md) соглашение о вызовах и компилятор выдает это предупреждение, если вы попытаетесь импортировать функции, помеченной `__clrcall`.

Следующий пример приводит к возникновению ошибки C4272:

```
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```