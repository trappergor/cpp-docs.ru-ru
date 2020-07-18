---
title: Предупреждение компилятора (уровень 1) C4293
description: Описывает причины C4293 компилятора КОМПИЛЯТОРОМ MSVC и показывает, как их исправить.
ms.date: 07/15/2020
f1_keywords:
- C4293
helpviewer_keywords:
- C4293
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
ms.openlocfilehash: 3b5a05d4a744b084f1cc34210a5374962064e85d
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446480"
---
# <a name="compiler-warning-level-1-c4293"></a>Предупреждение компилятора (уровень 1) C4293

> "*оператор*": число сдвигов отрицательное или слишком большое, неопределенное поведение

Если число сдвигов отрицательное или слишком велико, поведение полученного изображения не определено.

## <a name="remarks"></a>Комментарии

Чтобы устранить эту проблему, можно использовать приведение к первому операнду, чтобы развернуть его до размера типа результата.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4293 и демонстрирует способы его исправления:

```cpp
// C4293.cpp
// compile with: /c /W1
unsigned __int64 combine (unsigned lo, unsigned hi)
{
   return (hi << 32) | lo;   // C4293

   // In C, try the following line instead:
   // return ( (unsigned __int64)hi << 32) | lo;
   // In C++, try this line instead:
   // return (static_cast<unsigned __int64>(hi) << 32) | lo;
}
```
