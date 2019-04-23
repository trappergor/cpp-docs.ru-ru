---
title: Предупреждение компилятора C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: b5afb829485e0e9533a14e818e6d6785f268a83b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776367"
---
# <a name="compiler-warning-c4485"></a>Предупреждение компилятора C4485

«переопределяющая_функция»: соответствует методу базового класса «базового класса», но не «new» или «override»; предполагается «new» (и «virtual»)

Переопределяет метод доступа, с или без `virtual` ключевое слово, функцию доступа базового класса, но `override` или `new` описатель не была частью переопределения сигнатуры функции. Добавить `new` или `override` описатель, чтобы устранить это предупреждение.

См. в разделе [переопределить](../../extensions/override-cpp-component-extensions.md) и [new (новый слот в vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) Дополнительные сведения.

C4485 всегда выдается как ошибка. Используйте [предупреждение](../../preprocessor/warning.md) директиву pragma, чтобы отключить предупреждение C4485.

## <a name="example"></a>Пример

В следующем примере возникает предупреждение C4485

```
// C4485.cpp
// compile with: /clr
delegate void Del();

ref struct A {
   virtual event Del ^E;
};

ref struct B : A {
   virtual event Del ^E;   // C4485
};

ref struct C : B {
   virtual event Del ^E {
      void raise() override {}
      void add(Del ^) override {}
      void remove(Del^) override {}
   }
};
```