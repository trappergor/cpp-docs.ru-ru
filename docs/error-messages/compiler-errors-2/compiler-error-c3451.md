---
title: Ошибка компилятора C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: d6a0d1234d8f25c6a55fffa7170f37aae27f5817
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501321"
---
# <a name="compiler-error-c3451"></a>Ошибка компилятора C3451

"атрибут": невозможно применить неуправляемый атрибут к "Type"

Атрибут C++ не может применяться к типу CLR. Дополнительные сведения см. в [справочнике по атрибутам C++](../../windows/attributes/attributes-alphabetical-reference.md) .

Для получения дополнительной информации см. [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md).

Эта ошибка может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio 2005: атрибут [UUID](../../windows/attributes/uuid-cpp-attributes.md) больше не разрешается для определяемого пользователем атрибута с помощью программирования CLR. Используйте вместо этого <xref:System.Runtime.InteropServices.GuidAttribute>.

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
