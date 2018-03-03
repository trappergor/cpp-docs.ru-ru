---
title: "C3615 Ошибка компилятора | Документы Microsoft"
ms.date: 10/24/2017
ms.technology:
- cpp-tools
ms.topic: error-reference
f1_keywords:
- C3615
dev_langs:
- C++
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea5502ee6e66cf3add4a4ff97e4922a66712ed70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3615"></a>C3615 ошибки компилятора

> функция constexpr "*функция*" не может быть выражение константы

Функция *функция* не может быть вычислено как `constexpr` во время компиляции. Чтобы быть `constexpr`, функция может вызывать только другой `constexpr` функции.

## <a name="example"></a>Пример

Visual Studio 2017 г правильно выдает ошибку, если левый операнд в операции условно вычисление является недопустимым в `constexpr` контекста. Приведенный ниже код компилируется в Visual Studio 2015, но не в Visual Studio 2017 г.

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

Чтобы устранить эту проблему, объявите `array::size()` функционировать как `constexpr` или удалите `constexpr` квалификатор из `f`.