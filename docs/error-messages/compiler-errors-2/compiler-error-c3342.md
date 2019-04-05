---
title: Ошибка компилятора C3342
ms.date: 11/04/2016
f1_keywords:
- C3342
helpviewer_keywords:
- C3342
ms.assetid: 5c6d784f-bebe-4f7e-8615-44ca6f78bfba
ms.openlocfilehash: 822da2a04446938e49b3190d01c6252585b90ce6
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781787"
---
# <a name="compiler-error-c3342"></a>Ошибка компилятора C3342

"атрибут": неоднозначный атрибут

Компилятор обнаружил несколько определений атрибута.

Атрибут определен несколько раз.

Дополнительные сведения см. в разделе [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3342:

```
// C3342.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Reflection;

[AttributeUsage(AttributeTargets::All)]
public ref class XAttribute : public  Attribute {};

[AttributeUsage(AttributeTargets::All)]
public ref class X : public Attribute {};

[X]   // C3342 could refer to X or XAttribute
// try the following line instead
// [XAttribute]
public ref class Class4 {};
```