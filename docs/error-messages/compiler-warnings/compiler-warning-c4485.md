---
title: Предупреждение компилятора C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: d730441772f021bbece9af8313229543e432b2d7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87197297"
---
# <a name="compiler-warning-c4485"></a>Предупреждение компилятора C4485

"override_function": соответствует методу базового класса ссылки "base_class_function", но не помечен как "New" или "override"; предполагается "New" (и "Virtual")

Метод доступа переопределяет, с ключевым словом или без него — **`virtual`** функцией доступа базового класса, но `override` **`new`** спецификатор или не был частью переопределяющей сигнатуры функции. Добавьте **`new`** описатель или, `override` чтобы устранить это предупреждение.

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
