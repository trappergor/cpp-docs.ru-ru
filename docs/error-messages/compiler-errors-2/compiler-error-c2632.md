---
title: Ошибка компилятора C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: f69d43bf50f5f13957e49d1e9ffa798a3db5a7b3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754697"
---
# <a name="compiler-error-c2632"></a>Ошибка компилятора C2632

"тип1", за которым следует "тип2", недопустим

Эта ошибка может быть вызвана отсутствием кода между двумя описателями типа.

Следующий пример приводит к возникновению ошибки C2632:

```cpp
// C2632.cpp
int float i;   // C2632
```

Эта ошибка также может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio .NET 2003. `bool` теперь является правильным типом. В предыдущих версиях `bool` был typedef, и можно было создавать идентификаторы с таким именем.

Следующий пример приводит к возникновению ошибки C2632:

```cpp
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Чтобы устранить эту ошибку, чтобы код был допустимым в версиях Visual Studio .NET 2003 и Visual Studio .NET C++, переименуйте идентификатор.
