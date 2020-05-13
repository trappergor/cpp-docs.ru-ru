---
title: Ошибка компилятора C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: c1a5b6edbc87e14de267cf962dc2b1a71dd6be12
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200542"
---
# <a name="compiler-error-c3615"></a>Ошибка компилятора C3615

> Функция constexpr "*функция*" не может привести к константному выражению

Не удалось вычислить *функцию* функции как `constexpr` во время компиляции. Для `constexpr`функция может вызывать только другие функции `constexpr`.

## <a name="example"></a>Пример

Visual Studio 2017 правильно выдает ошибку, если левый операнд операции условно-оценки не является допустимым в контексте `constexpr`. Следующий код компилируется в Visual Studio 2015, но не в Visual Studio 2017.

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

Чтобы устранить эту проблему, либо объявите функцию `array::size()` как `constexpr` или удалите квалификатор `constexpr` из `f`.
