---
title: Ошибка компилятора C3114
ms.date: 11/04/2016
f1_keywords:
- C3114
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
ms.openlocfilehash: 6f548c72a0e95c533ed711fe9f2583a7abd6c500
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760765"
---
# <a name="compiler-error-c3114"></a>Ошибка компилятора C3114

"аргумент": недопустимый именованный аргумент атрибута

Чтобы член данных класса атрибута был допустимым именованным аргументом, он не должен быть помечен как `static`, `const`или `literal`. Если свойство, свойство не должно быть `static` и должно иметь методы доступа get и Set.

Дополнительные сведения см. в разделе [Свойства](../../extensions/property-cpp-component-extensions.md) и [определяемые пользователем атрибуты](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3114.

```cpp
// C3114.cpp
// compile with: /clr /c
public ref class A : System::Attribute {
public:
   static property int StaticProp {
      int get();
   }

   property int Prop2 {
      int get();
      void set(int i);
   }
};

[A(StaticProp=123)]   // C3114
public ref class R {};

[A(Prop2=123)]   // OK
public ref class S {};
```
