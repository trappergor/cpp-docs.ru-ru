---
title: Предупреждение компилятора C4485 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4485
dev_langs:
- C++
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb83700bf8ca79960599d85ed3d335f80c9fc7f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117755"
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