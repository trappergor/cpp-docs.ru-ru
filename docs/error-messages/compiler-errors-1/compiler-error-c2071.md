---
title: Ошибка компилятора C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 1dc9781bc0cf1bc6c7f879cc3971828983471c6f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757752"
---
# <a name="compiler-error-c2071"></a>Ошибка компилятора C2071

'идентификатор' : недопустимый класс хранилища

`identifier` был объявлен с недопустимым [классом хранения](../../c-language/c-storage-classes.md). Эта ошибка может возникнуть, когда для идентификатора указано несколько классов хранилища или когда определение несовместимо с объявлением класса хранилища.

Чтобы устранить эту проблему, изучите предполагаемый класс хранения идентификатора, например `static` или `extern`, и исправьте объявление в соответствие.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2071.

```cpp
// C2071.cpp
// compile with: /c
struct C {
   extern int i;   // C2071
};
struct D {
   int i;   // OK, no extern on an automatic
};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2071.

```cpp
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```
