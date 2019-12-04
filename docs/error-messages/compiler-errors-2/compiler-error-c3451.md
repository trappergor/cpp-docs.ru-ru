---
title: Ошибка компилятора C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: 2e0122dd53ba5318077dd33f22a07492c52db26b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756218"
---
# <a name="compiler-error-c3451"></a>Ошибка компилятора C3451

"атрибут": невозможно применить неуправляемый атрибут к "Type"

C++ Атрибут не может быть применен к типу CLR. Дополнительные сведения см [ C++ . в справочнике по атрибутам](../../windows/attributes/attributes-alphabetical-reference.md) .

Для получения дополнительной информации см. [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md).

Эта ошибка может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio 2005: атрибут [UUID](../../windows/uuid-cpp-attributes.md) больше не разрешается для определяемого пользователем атрибута с помощью программирования CLR. Взамен рекомендуется использовать <xref:System.Runtime.InteropServices.GuidAttribute>.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3451.

```cpp
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
