---
title: Ошибка компилятора C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 95344b5ef675f566f433dfeaed9dee5c38ef77d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598280"
---
# <a name="compiler-error-c2071"></a>Ошибка компилятора C2071

'идентификатор' : недопустимый класс хранилища

`identifier` был объявлен с недопустимым [класс хранения](../../c-language/c-storage-classes.md). Эта ошибка может возникнуть, когда для идентификатора указано несколько классов хранилища или когда определение несовместимо с объявлением класса хранилища.

Чтобы устранить эту проблему, узнайте нужный класс хранилища идентификатора — например, `static` или `extern`— и исправьте его объявление для сопоставления.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2071.

```
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

```
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```