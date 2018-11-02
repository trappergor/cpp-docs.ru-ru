---
title: Предупреждение компилятора (уровень 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: dee087b73bf032a68daf0527ea584efcc7579361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552637"
---
# <a name="compiler-warning-level-4-c4232"></a>Предупреждение компилятора (уровень 4) C4232

использовано нестандартное расширение: «идентификатор»: адрес dllimport «dllimport» не является статическим, идентичность не гарантируется

Расширения Microsoft (/Ze), можно передать нестатическое значение как адрес функции, объявленные с **dllimport** модификатор. В режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), это приводит к ошибке.

Следующий пример приводит к возникновению ошибки C4232:

```
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```