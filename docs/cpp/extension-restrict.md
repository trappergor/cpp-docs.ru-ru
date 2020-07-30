---
title: __restrict
ms.date: 10/10/2018
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
ms.openlocfilehash: 6318e6d78f6c4c4bb6827a79d26bca028dfe3f3f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233747"
---
# <a name="__restrict"></a>__restrict

Как и в случае с модификатором **__declspec ( [restrict](../cpp/restrict.md) )** , **`__restrict`** ключевое слово указывает, что символ не имеет псевдонима в текущей области. **`__restrict`** Ключевое слово отличается от `__declspec ( restrict )` модификатора следующими способами.

- **`__restrict`** Ключевое слово допустимо только для переменных и `__declspec ( restrict )` допустимо только в объявлениях и определениях функций.

- **`__restrict`** аналогичен **`restrict`** спецификации C99, но **`__restrict`** может использоваться в программах на C++ или C.

- Если **`__restrict`** используется, компилятор не распространяет свойство переменной без псевдонима. Это значит, что при присвоении **`__restrict`** переменной значения, не являющегося **`__restrict`** переменной, компилятор по-прежнему будет разрешать псевдониму не__restrict переменной. Это отличается от поведения **`restrict`** ключевого слова из спецификации C99.

Как правило, если вы намереваетесь подействовать на поведение всей функции, вместо этого ключевого слова лучше использовать `__declspec ( restrict )`.

Для совместимости с предыдущими версиями **_restrict** является синонимом, **`__restrict`** если только параметр компилятора [/Za не \( отключил расширения языка)](../build/reference/za-ze-disable-language-extensions.md) указан.

В Visual Studio 2015 и более поздних версий **`__restrict`** можно использовать ссылки на C++.

> [!NOTE]
> При использовании в переменной, которая также имеет ключевое слово [volatile](../cpp/volatile-cpp.md) , имеет **`volatile`** приоритет.

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

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)
