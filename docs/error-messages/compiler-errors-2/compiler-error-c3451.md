---
title: Ошибка компилятора C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: 5ef4352101541391a7cda88471fbaa6aeae4ffb4
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770373"
---
# <a name="compiler-error-c3451"></a>Ошибка компилятора C3451

«атрибут»: невозможно применить неуправляемый атрибут в «тип»

Атрибут C++ не может применяться к типу CLR. См. в разделе [Справочник по атрибутам C++](../../windows/attributes/attributes-alphabetical-reference.md) Дополнительные сведения.

Дополнительные сведения см. в разделе [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md).

Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: [uuid](../../windows/uuid-cpp-attributes.md) атрибут больше не разрешен в пользовательском атрибуте, с помощью программирования в среде CLR. Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.GuidAttribute>.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3451.

```
// C3451.cpp
// compile with: /clr /c
using namespace System;
[ attribute(AttributeTargets::All) ]
public ref struct MyAttr {};

[ MyAttr, helpstring("test") ]   // C3451
// try the following line instead
// [ MyAttr ]
public ref struct ABC {};
```