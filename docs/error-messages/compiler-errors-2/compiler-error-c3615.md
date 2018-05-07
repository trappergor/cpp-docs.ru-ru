---
title: C3615 Ошибка компилятора | Документы Microsoft
ms.date: 10/24/2017
ms.technology:
- cpp-diagnostics
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
ms.workload:
- cplusplus
ms.openlocfilehash: ce1ab43f8e15535614cedf43dba42fef882bf87a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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