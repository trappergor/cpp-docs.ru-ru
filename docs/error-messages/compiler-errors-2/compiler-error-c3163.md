---
title: Ошибка компилятора C3163 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e712a70bdd443d9a6c640853b958f29dac78dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061972"
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

[Заметки SAL](../../c-runtime-library/sal-annotations.md)