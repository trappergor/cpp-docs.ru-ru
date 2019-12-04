---
title: Ошибка компилятора C2364
ms.date: 11/04/2016
f1_keywords:
- C2364
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
ms.openlocfilehash: fb019d729bc100296742b15ba95460fe0e404673
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759884"
---
# <a name="compiler-error-c2364"></a>Ошибка компилятора C2364

"тип": недопустимый тип настраиваемого атрибута

Именованные аргументы для настраиваемых атрибутов ограничены константами времени компиляции. Например, целочисленные типы (int, char и т. д.), System:: Type ^ и System:: Object ^.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2364.

```cpp
// c2364.cpp
// compile with: /clr /c
using namespace System;

[attribute(AttributeTargets::All)]
public ref struct ABC {
public:
   // Delete the following line to resolve.
   ABC( Enum^ ) {}   // C2364
   ABC( int ) {}   // OK
};
```
