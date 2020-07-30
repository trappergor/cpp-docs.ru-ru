---
title: Ошибка компилятора C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: 17a210e2a514af1ffd62bf38651c4d17bd1fe32b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230796"
---
# <a name="compiler-error-c3615"></a>Ошибка компилятора C3615

> Функция constexpr "*функция*" не может привести к константному выражению

Не удалось вычислить *функцию* функции **`constexpr`** во время компиляции. **`constexpr`** Функция может вызывать только другие **`constexpr`** функции.

## <a name="example"></a>Пример

Visual Studio 2017 правильно выдает ошибку, если левый операнд операции условно-оценки не является допустимым в **`constexpr`** контексте. Следующий код компилируется в Visual Studio 2015, но не в Visual Studio 2017.

```cpp
// C3615.cpp
// Compile with: /c

template<int N>
struct myarray
{
    int size() const { return N; }
};

constexpr bool f(const myarray<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 starting in Visual Studio 2017
}
```

Чтобы устранить эту проблему, либо объявите `array::size()` функцию, **`constexpr`** либо удалите **`constexpr`** квалификатор из `f` .
