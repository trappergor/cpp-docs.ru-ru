---
title: Ошибка компилятора C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: eda3910c99f4c8ea96568f2d475c5d6a1e4cdc7c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041050"
---
# <a name="compiler-error-c3163"></a>Ошибка компилятора C3163

«construct»: атрибуты несовместимы с предыдущим объявлением

Атрибуты, применяемые к определению, конфликтуют с атрибутами, которые применяются к объявлению.

Для устранения ошибки C3163 рекомендуется атрибутов из опережающего объявления. Какие-либо атрибуты для опережающего объявления должны быть меньше, чем атрибуты в определении или, в основном равны им.

Возможная причина ошибки C3163 включает в себя язык заметки исходного кода Microsoft (SAL). Макросы SAL не расширяться, если при компиляции проекта с помощью **/ analyze** флаг. Это программа, которая компилируется без ошибок без / analyze может создавать ошибку C3163 при попытке ее повторной компиляции с / analyze-параметр. Дополнительные сведения о языке SAL см. в разделе [примечания SAL](../../c-runtime-library/sal-annotations.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3163.

```
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>См. также

[Примечания SAL](../../c-runtime-library/sal-annotations.md)