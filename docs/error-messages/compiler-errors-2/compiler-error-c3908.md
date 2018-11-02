---
title: Ошибка компилятора C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 84b21f20cbc8203a9cd70e487738c34c6ad3a89b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598936"
---
# <a name="compiler-error-c3908"></a>Ошибка компилятора C3908

уровень доступа, менее строгим, чем «конструкция»

Метод доступа свойства (get или set) не может иметь менее строгий доступ, чем доступ, заданный на само свойство.  Аналогично для методов доступа к событию.

Дополнительные сведения см. в разделе [свойство](../../windows/property-cpp-component-extensions.md) и [событий](../../windows/event-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3908:

```
// C3908.cpp
// compile with: /clr
ref class X {
protected:
   property int i {
   public:   // C3908 property i is protected
      int get();
   private:
      void set(int);   // OK more restrictive
   };
};
```