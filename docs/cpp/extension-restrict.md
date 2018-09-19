---
title: __restrict | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d9754f8b0b218fc4d627eb0e27504e8521bf776
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076441"
---
# <a name="restrict"></a>__restrict

Как и **__declspec ( [ограничить](../cpp/restrict.md) )** модификатор, **__restrict** слово указывает, что символ не является псевдонимом в текущей области. **__Restrict** ключевое слово отличается от `__declspec ( restrict )` модификатор одним из следующих способов:

- **__Restrict** ключевое слово может использоваться только для переменных, и `__declspec ( restrict )` допустим только в объявлениях и определениях функций.

- **__restrict** аналогичен **ограничить** из спецификации C99, но **__restrict** можно использовать в программах на C++ или C.

- Когда **__restrict** — используется, компилятор не распространяет свойство переменной нет-alias. То есть если назначить **__restrict** переменных, отличному от **__restrict** переменной, компилятор по-прежнему сможет не __restrict переменной, для которого создается псевдоним. Это отличается от поведения **ограничить** ключевое слово из спецификации C99.

Как правило, если вы намереваетесь подействовать на поведение всей функции, вместо этого ключевого слова лучше использовать `__declspec ( restrict )`.

В Visual Studio 2015 и более поздних версиях **__restrict** может использоваться для ссылок C++.

> [!NOTE]
>  При использовании на переменную, которая также имеет [volatile](../cpp/volatile-cpp.md) ключевое слово, **volatile** будет иметь приоритет.

## <a name="example"></a>Пример

```cpp
// __restrict_keyword.c
// compile with: /LD
// In the following function, declare a and b as disjoint arrays
// but do not have same assurance for c and d.
void sum2(int n, int * __restrict a, int * __restrict b,
          int * c, int * d) {
   int i;
   for (i = 0; i < n; i++) {
      a[i] = b[i] + c[i];
      c[i] = b[i] + d[i];
    }
}

// By marking union members as __restrict, tell compiler that
// only z.x or z.y will be accessed in any given scope.
union z {
   int * __restrict x;
   double * __restrict y;
};
```

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)