---
title: Ошибка компилятора C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: e966295b5ab63350828ddb73d6791a9e30bb5c59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404108"
---
# <a name="compiler-error-c3615"></a>Ошибка компилятора C3615

> функция constexpr "*функция*" не может быть константным выражением

Функция *функция* не может быть вычислено как `constexpr` во время компиляции. Чтобы быть `constexpr`, функцию можно вызывать только другой `constexpr` функции.

## <a name="example"></a>Пример

Visual Studio 2017 правильно выдает ошибку, если левый операнд операции условного вычисления является недопустимым в `constexpr` контекста. Следующий код компилируется в Visual Studio 2015, но не в Visual Studio 2017.

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

Чтобы устранить эту проблему, либо объявить `array::size()` функционировать как `constexpr` или удалите `constexpr` квалификатора `f`.