---
title: Ошибка компилятора C3530 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5866e2ea44b84f3afeb0cef8423abc28f8e056ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094797"
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