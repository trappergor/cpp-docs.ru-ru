---
title: Ошибка компилятора C3095
ms.date: 11/04/2016
f1_keywords:
- C3095
helpviewer_keywords:
- C3095
ms.assetid: cde725be-0936-40f6-9e57-e1d7d0710f83
ms.openlocfilehash: b8b6a7bfd5b44e0ddd1e8dfba1a054d9645a4693
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438757"
---
# <a name="compiler-error-c3095"></a>Ошибка компилятора C3095

"атрибут": повтор атрибута невозможен

Некоторые атрибуты объявляются таким образом, что множественное применение атрибута к целевому объекту не допускается.

Дополнительные сведения см. в разделе [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3095:

```
// C3095.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All, AllowMultiple=false)]
public ref class Attr : public Attribute {
public:
   Attr(int t) : m_t(t) {}
   const int m_t;
};

[AttributeUsage(AttributeTargets::All, AllowMultiple=true)]
public ref class Attr2 : public Attribute {
public:
   Attr2(int t) : m_t(t) {}
   const int m_t;
};

[Attr(10)]   // C3095
[Attr(11)]
ref class A {};

[Attr2(10)]   // OK
[Attr2(11)]
ref class B {};
```