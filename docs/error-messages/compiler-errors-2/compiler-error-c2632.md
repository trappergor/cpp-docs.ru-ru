---
title: Ошибка компилятора C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: 8ea3a106e8819bf067203f220ca51e17b87bfe46
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225466"
---
# <a name="compiler-error-c2632"></a>Ошибка компилятора C2632

"тип1", за которым следует "тип2", недопустим

Эта ошибка может быть вызвана отсутствием кода между двумя описателями типа.

Следующий пример приводит к возникновению ошибки C2632:

```cpp
// C2632.cpp
int float i;   // C2632
```

Эта ошибка также может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio .NET 2003. **`bool`** теперь является правильным типом. В предыдущих версиях **`bool`** использовался typedef, и можно было бы создать идентификаторы с таким именем.

Следующий пример приводит к возникновению ошибки C2632:

```cpp
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Чтобы устранить эту ошибку, чтобы код был допустимым в версиях Visual Studio .NET 2003 и Visual Studio .NET Visual C++, переименуйте идентификатор.
