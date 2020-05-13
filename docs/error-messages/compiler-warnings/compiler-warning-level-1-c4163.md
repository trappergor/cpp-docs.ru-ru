---
title: Предупреждение компилятора (уровень 1) C4163
ms.date: 11/04/2016
f1_keywords:
- C4163
helpviewer_keywords:
- C4163
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
ms.openlocfilehash: 492fe4a75b4ddf9b5f78810226f14aa84ab2b56a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176134"
---
# <a name="compiler-warning-level-1-c4163"></a>Предупреждение компилятора (уровень 1) C4163

"идентификатор": недоступен в качестве подставляемой функции

Указанная функция не может использоваться как [встроенная](../../preprocessor/intrinsic.md) функция. Компилятор игнорирует неправильное имя функции.

Следующий пример приводит к возникновению ошибки C4163.

```cpp
// C4163.cpp
// compile with: /W1 /LD
#include <math.h>
#pragma intrinsic(mysin)   // C4163
// try the following line instead
// #pragma intrinsic(sin)
```
