---
title: Ошибка компилятора C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: b8d516074b79704b10d27dd4638585a5ada08323
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510130"
---
# <a name="compiler-error-c3532"></a>Ошибка компилятора C3532

"тип": неправильное использование "Auto"

Указанный тип не может быть объявлен с **`auto`** ключевым словом. Например, нельзя использовать **`auto`** ключевое слово для объявления массива или возвращаемого типа метода.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что выражение инициализации возвращает допустимый тип.

1. Убедитесь, что не объявлен тип возвращаемого значения массива или метода.

## <a name="examples"></a>Примеры

В следующем примере создается C3532, поскольку **`auto`** ключевое слово не может объявлять тип возвращаемого значения метода.

```cpp
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

В следующем примере выдается C3532, так как **`auto`** ключевое слово не может объявлять массив.

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

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-cpp.md)
