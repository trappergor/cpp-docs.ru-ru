---
title: Ошибка компилятора C3668
ms.date: 11/04/2016
f1_keywords:
- C3668
helpviewer_keywords:
- C3668
ms.assetid: 53a96698-bde4-4447-95b5-b5108291f60c
ms.openlocfilehash: 7bc03050518055bb3167ee2ce9d1e1fcd88b59b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504564"
---
# <a name="compiler-error-c3668"></a>Ошибка компилятора C3668

«метод»: метод со спецификатором переопределения «override» не выполняли переопределение методов базового класса

Функция, предпринята попытка переопределения несуществующей функции.

Дополнительные сведения см. в разделе [явное переопределение](../../windows/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3668.

```
// C3668.cpp
// compile with: /c
__interface I {
   void f(int);   // virtual by default
};

class J {
public:
   void g(int);
   virtual void h(int);
};

struct R : I,J {
   virtual void f() override {}   // C3668
   virtual void f(int) override {}   // OK

   virtual void g(int) override {}   // C3668
   virtual void h(int) override {}   // OK
};
```