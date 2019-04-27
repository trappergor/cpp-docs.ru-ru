---
title: Ошибка компилятора C3290
ms.date: 11/04/2016
f1_keywords:
- C3290
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
ms.openlocfilehash: f2a346354d8da7d78c5517b01b4438bfb8af50ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222711"
---
# <a name="compiler-error-c3290"></a>Ошибка компилятора C3290

"тип": тривиальное свойство не может иметь ссылочный тип

Свойство объявлено неправильно. При объявлении обычного свойства компилятор создает переменную, которую будет обновлять свойство. В классе не может присутствовать ссылочная переменная с отслеживанием.

См. в разделе [свойство](../../extensions/property-cpp-component-extensions.md) и [оператор отслеживания ссылок](../../extensions/tracking-reference-operator-cpp-component-extensions.md) Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3290:

```
// C3290.cpp
// compile with: /clr /c
ref struct R {};

ref struct X {
   R^ mr;

   property R % y;   // C3290
   property R ^ x;   // OK

   // OK
   property R% prop {
      R% get() {
         return *mr;
      }

      void set(R%) {}
   }
};

int main() {
   X x;
   R% xp = x.prop;
}
```