---
title: Предупреждение компилятора (уровень 4) C4296
ms.date: 11/04/2016
f1_keywords:
- C4296
helpviewer_keywords:
- C4296
ms.assetid: 9d99aafe-f6bd-4ee0-b8d0-98ce5712274d
ms.openlocfilehash: 74a2df69120436d0bb3a0a02809a1523a3766445
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624652"
---
# <a name="compiler-warning-level-4-c4296"></a>Предупреждение компилятора (уровень 4) C4296

«operator»: выражение всегда имеет значение false

Переменной без знака использовался в операции сравнения с нуля.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4296:

```
// C4296.cpp
// compile with: /W4
#pragma warning(default : 4296)
int main()
{
   unsigned int u = 9;
   if (u < 0)    // C4296
      u++;
   if (u >= 0)   // C4296
      u++;
}
```