---
title: Ошибка компилятора C2061
ms.date: 11/04/2016
f1_keywords:
- C2061
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
ms.openlocfilehash: 1e1b13960c84d4e03c6316c451c690f8b5a6236e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212869"
---
# <a name="compiler-error-c2061"></a>Ошибка компилятора C2061

Синтаксическая ошибка: идентификатор "идентификатор"

Компилятор обнаружил идентификатор, в котором он не ожидался. Убедитесь, что `identifier` объявлено перед использованием.

Инициализатор может быть заключен в круглые скобки. Чтобы избежать этой проблемы, заключите декларатор в круглые скобки или сделайте его **`typedef`** .

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
