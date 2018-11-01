---
title: Ошибка компилятора C3207
ms.date: 11/04/2016
f1_keywords:
- C3207
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
ms.openlocfilehash: 51873e089499e42f4ddeb97c95e3f18416df447c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515496"
---
# <a name="compiler-error-c3207"></a>Ошибка компилятора C3207

"функция": недопустимый аргумент шаблона для "аргумент", требуется класс шаблона

Функция шаблона определена как принимающая аргумент шаблона. Однако передан аргумент типа шаблона.

Следующий пример приводит к возникновению ошибки C3207:

```
// C3207.cpp
template <template <class T> class TT>
void f(){}

template <class T>
struct S
{
};

void f1()
{
   f<S<int> >();   // C3207
   // try the following line instead
   // f<S>();
}
```