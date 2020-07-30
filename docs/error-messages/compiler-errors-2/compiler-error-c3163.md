---
title: Ошибка компилятора C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: 29f810ab1ab1608ab9c0492c9f88b8edfe042168
ms.sourcegitcommit: 6e55aeb538b1c39af754f82d6f7738a18f5aa031
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87390030"
---
# <a name="compiler-error-c3163"></a>Ошибка компилятора C3163

> "*конструкция*": атрибуты несовместимы с предыдущим объявлением

Атрибуты, применяемые к определению, конфликтуют с атрибутами, применяемыми к объявлению.

Одним из способов разрешения C3163 является удаление атрибутов в прямом объявлении. Все атрибуты в прямом объявлении должны быть меньше атрибутов в определении или, как правило, равно им.

Возможной причиной ошибки C3163 является язык аннотирования исходного кода Microsoft (SAL). Макросы SAL не расширяются, если проект не компилируется с помощью **`/analyze`** флага. Программа, которая компилируется чисто без **`/analyze`** возможности создания C3163, если попытается перекомпилировать ее с **`/analyze`** параметром. Дополнительные сведения о SAL см. в разделе [аннотации SAL](../../c-runtime-library/sal-annotations.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3163.

```cpp
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>См. также

[Аннотации SAL](../../c-runtime-library/sal-annotations.md)
