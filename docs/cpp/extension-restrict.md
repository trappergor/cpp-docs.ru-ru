---
title: '`__restrict`'
description: Описывает `__restrict` ключевое слово Microsoft Visual C++.
ms.date: 11/6/2020
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.openlocfilehash: f23574f49712928e0095f29a3b88b0c05b185eab
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381575"
---
# `__restrict`

Как и модификатор **`__declspec` ( [`restrict`](../cpp/restrict.md) )** , **`__restrict`** ключевое слово (два символа подчеркивания "_") указывает, что символ не является псевдонимом в текущей области. **`__restrict`** Ключевое слово отличается от `__declspec (restrict)` модификатора следующими способами.

- **`__restrict`** Ключевое слово допустимо только для переменных и `__declspec (restrict)` допустимо только в объявлениях и определениях функций.

- **`__restrict`** похож на [`restrict`](../c-language/type-qualifiers.md#restrict) C, начиная с C99, но **`__restrict`** может использоваться как в программах на C++, так и на языке c.

- Если **`__restrict`** используется, компилятор не распространяет свойство переменной без псевдонима. Это значит, что при присвоении **`__restrict`** переменной значения, не являющегося **`__restrict`** переменной, компилятор по-прежнему будет разрешать псевдониму не__restrict переменной. Это отличается от поведения **`restrict`** ключевого слова языка C C99.

Как правило, если вы хотите повлиять на поведение целой функции, используйте **`__declspec (restrict)`** вместо ключевого слова.

Для совместимости с предыдущими версиями аргумент **`_restrict`** является синонимом, **`__restrict`** если только параметр компилятора не [ `/Za` \( отключает расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

В Visual Studio 2015 и более поздних версий **`__restrict`** можно использовать ссылки на C++.

> [!NOTE]
> При использовании в переменной, которая также имеет [`volatile`](../cpp/volatile-cpp.md) ключевое слово, имеет **`volatile`** приоритет.

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
