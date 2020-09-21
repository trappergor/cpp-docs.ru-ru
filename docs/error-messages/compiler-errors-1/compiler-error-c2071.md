---
title: Ошибка компилятора C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 7619d968379bfc35e98bd87071b75296d10c382c
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743286"
---
# <a name="compiler-error-c2071"></a>Ошибка компилятора C2071

'идентификатор' : недопустимый класс хранилища

`identifier` объявлено с недопустимым [классом хранения](../../c-language/c-storage-classes.md). Эта ошибка может возникнуть, когда для идентификатора указано несколько классов хранилища или когда определение несовместимо с объявлением класса хранилища.

Чтобы устранить эту проблему, изучите предполагаемый класс хранения идентификатора, например или, **`static`** **`extern`** и исправьте объявление в соответствии с ним.

## <a name="examples"></a>Примеры

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

Следующий пример приводит к возникновению ошибки C2071.

```cpp
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```
