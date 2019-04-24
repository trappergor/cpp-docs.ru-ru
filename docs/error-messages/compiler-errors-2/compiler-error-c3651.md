---
title: Ошибка компилятора C3651
ms.date: 11/04/2016
f1_keywords:
- C3651
helpviewer_keywords:
- C3651
ms.assetid: a03e692e-c219-4654-9827-8415cfa5a22d
ms.openlocfilehash: 6e773201e3bc9a4edb1ee77f1ddcd555e0ae0c0e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779340"
---
# <a name="compiler-error-c3651"></a>Ошибка компилятора C3651

«член»: не может использоваться как явное переопределение, должен быть членом базового класса

Было указано явное переопределение, но переопределяемая функция была в типе, который не является базовым типом.

Дополнительные сведения см. в разделе [явное переопределение](../../extensions/explicit-overrides-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3651:

```
// C3651.cpp
// compile with: /clr /c
ref class C {
public:
   virtual void func2();
};

ref class Other {
public:
   virtual void func();
};

ref class D : public C {
public:
   virtual void func() new sealed = Other::func;   // C3651
   virtual void func2() new sealed = C::func2;   // OK
};
```