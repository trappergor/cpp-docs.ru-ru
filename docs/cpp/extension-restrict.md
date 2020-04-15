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
ms.openlocfilehash: 27ac76251456d9a0bf5908ad6d1fc2bee7534e9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360815"
---
# <a name="__restrict"></a>__restrict

Как и модификатор **__declspec [(ограничиваем),](../cpp/restrict.md) ** **ключевое** слово __restrict указывает на то, что символ не псевдоним в текущей области. Ключевое слово **__restrict** отличается от модификатора `__declspec ( restrict )` следующим образом:

- **Ключевое** слово __restrict действителен только `__declspec ( restrict )` по переменным и действителен только в декларациях и определениях функций.

- **__restrict** похож на **ограничение** от спецификации C99, но **__restrict** может быть использован в программах C или C.

- При **использовании __restrict** компилятор не будет распространять свойство переменной без псевдонима. То есть, если назначить **__restrict** переменную**не-__restrict** переменной, компилятор по-прежнему позволит не-__restrict переменной, которая будет псевдонимом. Это отличается от поведения ключевого слова **ограничения** от спецификации C99.

Как правило, если вы намереваетесь подействовать на поведение всей функции, вместо этого ключевого слова лучше использовать `__declspec ( restrict )`.

Для совместимости с предыдущими версиями **_restrict** является синонимом **для __restrict** если не указан абонементы компилятора [/ расширения языка с помощью qA \(Disable.](../build/reference/za-ze-disable-language-extensions.md)

В Visual Studio 2015 и позже, **__restrict** может быть использован на ссылки СЗ.

> [!NOTE]
> При использовании на переменной, которая также имеет [летучих](../cpp/volatile-cpp.md) ключевое слово, **летучих** будет иметь приоритет.

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

[Keywords](../cpp/keywords-cpp.md)
