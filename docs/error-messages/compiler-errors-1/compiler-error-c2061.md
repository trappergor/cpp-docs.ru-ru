---
title: Ошибка компилятора C2061
ms.date: 11/04/2016
f1_keywords:
- C2061
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
ms.openlocfilehash: 0bd1e770e38fcb85164bfa205470ac55a12e1c87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466200"
---
# <a name="compiler-error-c2061"></a>Ошибка компилятора C2061

Синтаксическая ошибка: идентификатор «идентификатор»

Компилятор обнаружил идентификатор, где он не ожидался. Убедитесь, что `identifier` объявлена, прежде чем использовать его.

Инициализатор могут быть заключены в круглые скобки. Чтобы избежать этой проблемы, заключите декларатор в круглые скобки или сделайте его `typedef`.

Эта ошибка также может быть вызвана, когда компилятор обнаруживает выражение в качестве аргумента шаблона класса; Используйте [typename](../../cpp/typename.md) , чтобы сообщить компилятору, он является типом.

Следующий пример приводит к возникновению ошибки C2061:

```
// C2061.cpp
// compile with: /c
template < A a >   // C2061
// try the following line instead
// template < typename b >
class c{};
```

C2061 может возникать, если передать имя экземпляра для [typeid](../../windows/typeid-cpp-component-extensions.md):

```
// C2061b.cpp
// compile with: /clr
ref struct G {
   int i;
};

int main() {
   G ^ pG = gcnew G;
   System::Type ^ pType = typeid<pG>;   // C2061
   System::Type ^ pType2 = typeid<G>;   // OK
}
```