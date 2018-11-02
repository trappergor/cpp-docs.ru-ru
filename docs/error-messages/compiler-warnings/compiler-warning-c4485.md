---
title: Предупреждение компилятора C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: 7138f1a3cecaaf75fbab01fd1aee18529b7a3a84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652477"
---
# <a name="compiler-warning-c4485"></a>Предупреждение компилятора C4485

«переопределяющая_функция»: соответствует методу базового класса «базового класса», но не «new» или «override»; предполагается «new» (и «virtual»)

Переопределяет метод доступа, с или без `virtual` ключевое слово, функцию доступа базового класса, но `override` или `new` описатель не была частью переопределения сигнатуры функции. Добавить `new` или `override` описатель, чтобы устранить это предупреждение.

См. в разделе [переопределить](../../windows/override-cpp-component-extensions.md) и [new (новый слот в vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md) Дополнительные сведения.

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