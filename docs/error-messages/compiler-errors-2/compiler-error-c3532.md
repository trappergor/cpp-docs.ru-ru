---
title: Ошибка компилятора C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: 2ef5eb3c2bedd9defbd0b80e6d8c5c8912fcf16d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761937"
---
# <a name="compiler-error-c3532"></a>Ошибка компилятора C3532

"тип": неправильное использование "Auto"

Указанный тип не может быть объявлен с ключевым словом `auto`. Например, нельзя использовать ключевое слово `auto` для объявления массива или возвращаемого типа метода.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что выражение инициализации возвращает допустимый тип.

1. Убедитесь, что не объявлен тип возвращаемого значения массива или метода.

## <a name="example"></a>Пример

Следующий пример возвращает C3532, так как ключевое слово `auto` не может объявлять тип возвращаемого значения метода.

```cpp
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

## <a name="example"></a>Пример

В следующем примере выдается C3532, так как ключевое слово `auto` не может объявлять массив.

```cpp
// C3532b.cpp
// Compile with /Zc:auto
int main()
{
   int x[5];
   auto a[5];            // C3532
   auto b[1][2];         // C3532
   auto y[5] = x;        // C3532
   auto z[] = {1, 2, 3}; // C3532
   auto w[] = x;         // C3532
   return 0;
}
```

## <a name="see-also"></a>См. также:

[Ключевое слово auto](../../cpp/auto-keyword.md)
