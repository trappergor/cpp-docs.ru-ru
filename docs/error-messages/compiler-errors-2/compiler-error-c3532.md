---
title: Ошибка компилятора C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: 7b5d1fe61ae08811186e25547ccc3f33e3b0198e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397397"
---
# <a name="compiler-error-c3532"></a>Ошибка компилятора C3532

«Тип»: Неправильное использование «auto»

Указанный тип не может объявляться с `auto` ключевое слово. Например, нельзя использовать `auto` тип возвращаемого значения ключевого слова для объявления массива или метод.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что выражение инициализации возвращает допустимый тип.

1. Убедитесь, что вы не объявляйте массивом или типом возвращаемого значения метода.

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3532, поскольку `auto` ключевое слово не может объявить тип возвращаемого значения метода.

```
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3532, поскольку `auto` ключевое слово не может объявить массив.

```
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

[Ключевое слово auto](../../cpp/auto-keyword.md)