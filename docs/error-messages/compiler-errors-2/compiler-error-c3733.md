---
title: Ошибка компилятора C3733
ms.date: 11/04/2016
f1_keywords:
- C3733
helpviewer_keywords:
- C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
ms.openlocfilehash: 006f87691c6e0839115e2c02ab0d922aa95eaa93
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501651"
---
# <a name="compiler-error-c3733"></a>Ошибка компилятора C3733

«событие»: неправильный синтаксис для задания COM-события; Возможно, отсутствует «__interface»?

Неправильный синтаксис был использован для COM-события. Чтобы устранить эту ошибку, измените тип события или исправьте синтаксис, чтобы соответствовать требованиям к именам событий COM.

Следующий пример приводит к возникновению ошибки C3733:

```
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[coclass, event_source(com), // change 'com' to 'native' to resolve
uuid("00000000-0000-0000-0000-000000000001")]
class A
{
   __event void func();   // C3733
};

int main()
{
}
```