---
title: Предупреждение компилятора C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: c92f805eb2960336ed34f5da93b6c13f46bf15ac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165149"
---
# <a name="compiler-warning-c4485"></a>Предупреждение компилятора C4485

"override_function": соответствует методу базового класса ссылки "base_class_function", но не помечен как "New" или "override"; предполагается "New" (и "Virtual")

Метод доступа переопределяет, с ключевым словом `virtual` или без него — функцией доступа базового класса, но спецификатор `override` или `new` не был частью переопределяющей сигнатуры функции. Добавьте спецификатор `new` или `override`, чтобы устранить это предупреждение.

Дополнительные сведения см. в разделе [Переопределение](../../extensions/override-cpp-component-extensions.md) и [Создание нового слота в vtable](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) .

C4485 всегда выдается как ошибка. Чтобы отключить C4485, используйте директиву pragma [warning](../../preprocessor/warning.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4485

```cpp
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
