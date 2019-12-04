---
title: Ошибка компилятора C2061
ms.date: 11/04/2016
f1_keywords:
- C2061
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
ms.openlocfilehash: dc64852523b6b56bc506260576e3c79164628340
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735935"
---
# <a name="compiler-error-c2061"></a>Ошибка компилятора C2061

Синтаксическая ошибка: идентификатор "идентификатор"

Компилятор обнаружил идентификатор, в котором он не ожидался. Убедитесь, что `identifier` объявлен перед его использованием.

Инициализатор может быть заключен в круглые скобки. Чтобы избежать этой проблемы, заключите декларатор в круглые скобки или сделайте его `typedef`ом.

Эта ошибка также может быть вызвана тем, что компилятор обнаруживает выражение как аргумент шаблона класса; Используйте [TypeName](../../cpp/typename.md) , чтобы сообщить компилятору, что он является типом.

Следующий пример приводит к возникновению ошибки C2061:

```cpp
// C2061.cpp
// compile with: /c
template < A a >   // C2061
// try the following line instead
// template < typename b >
class c{};
```

C2061 может возникать, если имя экземпляра передается в [идентификатор typeid](../../extensions/typeid-cpp-component-extensions.md):

```cpp
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
