---
title: Ошибка компилятора C3749
ms.date: 11/04/2016
f1_keywords:
- C3749
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
ms.openlocfilehash: 75138bf8b090b7770d5bee918790efc095d76627
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761846"
---
# <a name="compiler-error-c3749"></a>Ошибка компилятора C3749

"атрибут": настраиваемый атрибут не может использоваться внутри функции

В функции нельзя использовать настраиваемый атрибут. Дополнительные сведения о настраиваемых атрибутах см. в разделе [атрибут](../../windows/attributes/attribute.md)раздела.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3749:

```cpp
// C3749a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
public ref struct ABC : public Attribute {
   ABC() {}
};

void f1() { [ABC]; };  // C3749
```
