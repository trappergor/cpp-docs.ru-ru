---
title: Ошибка компилятора C3451 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3451
dev_langs:
- C++
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8685b75684827b4f202317e1df72a8248f1b41dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085203"
---
# <a name="compiler-error-c3451"></a>Ошибка компилятора C3451

«атрибут»: невозможно применить неуправляемый атрибут в «тип»

Атрибут C++ не может применяться к типу CLR. См. в разделе [Справочник по атрибутам C++](../../windows/cpp-attributes-reference.md) Дополнительные сведения.

Дополнительные сведения см. в разделе [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).

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