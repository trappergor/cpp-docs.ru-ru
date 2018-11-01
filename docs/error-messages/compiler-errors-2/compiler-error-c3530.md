---
title: Ошибка компилятора C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 90f6000c7d4c4bfa0d610bd5942df0b958e47c60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643632"
---
# <a name="compiler-error-c3530"></a>Ошибка компилятора C3530

«auto» нельзя использовать вместе с любой другими описателями типа

Спецификатор типа используется с `auto` ключевое слово.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не используйте описатель типа в объявлении переменной, которая использует `auto` ключевое слово.

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3530, так как переменная `x` объявляется с обоими `auto` ключевое слово и тип `int`, и потому, что код примера компилируется с **/Zc: auto**.

```
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)