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
ms.openlocfilehash: cb340554bc20516175400c4d14a5d0dba934a313
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188965"
---
# <a name="__restrict"></a>__restrict

Как и в случае с модификатором **__declspec ( [restrict](../cpp/restrict.md) )** , ключевое слово **__restrict** указывает, что символ не имеет псевдонима в текущей области. Ключевое слово **__restrict** отличается от модификатора `__declspec ( restrict )` следующими способами:

- Ключевое слово **__restrict** допустимо только для переменных, а `__declspec ( restrict )` допустимы только в объявлениях и определениях функций.

- **__restrict** похож на **ограничение** спецификации C99, но **__restrict** может использоваться в C++ программах или C.

- Если используется **__restrict** , компилятор не распространяет свойство переменной без псевдонима. Это значит, что при присвоении переменной **__restrict** , не являющейся **__restrict** , компилятор по-прежнему будет разрешать присвоение псевдонима переменной, отличной от __restrict. Это отличается от поведения ключевого слова **restrict** из спецификации C99.

Как правило, если вы намереваетесь подействовать на поведение всей функции, вместо этого ключевого слова лучше использовать `__declspec ( restrict )`.

Для совместимости с предыдущими версиями **_restrict** является синонимом для **__restrict** , если только не указан параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

В Visual Studio 2015 и более поздних версиях **__restrict** можно использовать C++ для ссылок.

> [!NOTE]
>  При использовании в переменной, у которой также есть ключевое слово [volatile](../cpp/volatile-cpp.md) , приоритет будет иметь значение **volatile** .

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
