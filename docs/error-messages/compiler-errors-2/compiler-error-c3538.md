---
title: Ошибка компилятора C3538
ms.date: 11/04/2016
f1_keywords:
- C3538
helpviewer_keywords:
- C3538
ms.assetid: ef3698a5-7356-4c62-b9af-5d3a4baed958
ms.openlocfilehash: 290faa1a227920cd46f32a4adf0dd6a6f3687c6d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233370"
---
# <a name="compiler-error-c3538"></a>Ошибка компилятора C3538

в списке объявлений спецификатор "auto" должен всегда выводить тот же самый тип

Все переменные в списке объявлений не были разрешены в один тип.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что все объявления в списке выводятся на **`auto`** один и тот же тип.

## <a name="example"></a>Пример

Следующие выражения вызывают ошибку C3538. Каждый оператор объявляет несколько переменных, но каждое использование **`auto`** ключевого слова не приводит к одному и тому же типу.

```cpp
// C3538.cpp
// Compile with /Zc:auto
// C3538 expected
int main()
{
// Variable x1 is a pointer to char, but y1 is a double.
   auto * x1 = "a", y1 = 3.14;
// Variable c is a char and c1 is char*, but c2, and c3 are pointers to pointers.
   auto c = 'a', *c1 = &c, * c2 = &c1, * c3 = &c2;
// Variable x2 is an int, but y2 is a double and z is a char.
   auto x2(1), y2(0.0), z = 'a';
// Variable a is a pointer to int, but b is a pointer to double.
   auto *a = new auto(1), *b = new auto(2.0);
   return 0;
}
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)
