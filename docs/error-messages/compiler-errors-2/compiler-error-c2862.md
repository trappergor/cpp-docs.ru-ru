---
title: Ошибка компилятора C2862
ms.date: 11/04/2016
f1_keywords:
- C2862
helpviewer_keywords:
- C2862
ms.assetid: c04d8499-b799-48a1-9fb4-7902a0b0ac8e
ms.openlocfilehash: a3e2dba20c5283d87b6e98c2f8c9aba83c2d3cb9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449183"
---
# <a name="compiler-error-c2862"></a>Ошибка компилятора C2862

«интерфейс»: интерфейс может иметь только открытые члены

Защищенные и закрытые члены, которые могут осуществляться только из других функций-членов. Такие члены являются не используется в интерфейсе, так как он может не предоставлять реализации для любого из его элементов.

Следующий пример приводит к возникновению C2862:

```
// C2862.cpp
// compile with: /c
#include <unknwn.h>

[object, uuid="60719E20-EF37-11D1-978D-0000F805D73B"]
__interface IMyInterface {
   HRESULT mf1(void);   // OK
protected:
   HRESULT mf2(int *b);   // C2862
private:
   HRESULT mf3(int *c);   // C2862
};
```