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
ms.openlocfilehash: 76cdf9424e6eab33a3a92b3f98d9c2b0b04ff667
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183756"
---
# <a name="restrict"></a>__restrict

Как и **__declspec ( [ограничить](../cpp/restrict.md) )** модификатор, **__restrict** слово указывает, что символ не является псевдонимом в текущей области. **__Restrict** ключевое слово отличается от `__declspec ( restrict )` модификатор одним из следующих способов:

- **__Restrict** ключевое слово может использоваться только для переменных, и `__declspec ( restrict )` допустим только в объявлениях и определениях функций.

- **__restrict** аналогичен **ограничить** из спецификации C99, но **__restrict** может использоваться в C++ или программ на языке C.

- Когда **__restrict** — используется, компилятор не распространяет свойство переменной нет-alias. То есть если назначить **__restrict** переменных, отличному от **__restrict** переменной, компилятор по-прежнему сможет не __restrict переменной, для которого создается псевдоним. Это отличается от поведения **ограничить** ключевое слово из спецификации C99.

Как правило, если вы намереваетесь подействовать на поведение всей функции, вместо этого ключевого слова лучше использовать `__declspec ( restrict )`.

Для совместимости с предыдущими версиями **_restrict** является синонимом **__restrict** Если параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) — указан.

В Visual Studio 2015 и более поздних версиях **__restrict** можно установить на C++ ссылки.

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