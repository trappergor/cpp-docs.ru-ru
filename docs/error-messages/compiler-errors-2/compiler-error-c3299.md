---
title: Ошибка компилятора C3299
ms.date: 11/04/2016
f1_keywords:
- C3299
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
ms.openlocfilehash: 4ad48ea0bc09e098a41cb9aa969a08e9ead48f73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484844"
---
# <a name="compiler-error-c3299"></a>Ошибка компилятора C3299

"функция-член": невозможно указать ограничения, они унаследованы из базового метода

При переопределении универсальной функции-члена нельзя указать предложения ограничений (при повторении ограничений подразумевается, что они не наследуются).

В этом случае наследуются предложения ограничений, содержащиеся в переопределяемой универсальной функции.

Дополнительные сведения см. в разделе [ограничений для параметров универсального типа (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3299.

```
// C3299.cpp
// compile with: /clr /c
public ref struct R {
   generic<class T>
   where T : R
   virtual void f();
};

public ref struct S : R {
   generic<class T>
   where T : R   // C3299
   virtual void f() override;
};
```