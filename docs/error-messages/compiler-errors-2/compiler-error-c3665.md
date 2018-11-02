---
title: Ошибка компилятора C3665
ms.date: 11/04/2016
f1_keywords:
- C3665
helpviewer_keywords:
- C3665
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
ms.openlocfilehash: 30aaf67ac9f912059bb5726681e61feabc1e557d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644123"
---
# <a name="compiler-error-c3665"></a>Ошибка компилятора C3665

«деструктор»: спецификатор переопределения «ключевое слово», не разрешена для деструктора или метода завершения

Ключевое слово использовался, не разрешена для деструктора или метода завершения.

Например новый слот не может быть запрошены для деструктора или метода завершения.  Дополнительные сведения см. в разделе [явное переопределение](../../windows/explicit-overrides-cpp-component-extensions.md) и [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Следующий пример приводит к возникновению ошибки C3665:

```
// C3665.cpp
// compile with: /clr
public ref struct R {
   virtual ~R() { }
   virtual void a() { }
};

public ref struct S : R {
   virtual ~S() new {}   // C3665
   virtual void a() new {}   // OK
};
```