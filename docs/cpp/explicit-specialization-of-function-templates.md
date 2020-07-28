---
title: Явная специализация шаблонов функций
ms.date: 11/04/2016
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
ms.openlocfilehash: 638b5dbca1b3c0c9b9c9c946418ea70354ff6266
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220565"
---
# <a name="explicit-specialization-of-function-templates"></a>Явная специализация шаблонов функций

Используя шаблон функции, можно указать особое поведение для определенного типа, предоставив явную специализацию (переопределение) шаблона функции для этого типа. Пример:

```cpp
template<> void MySwap(double a, double b);
```

Это объявление позволяет определить другую функцию для **`double`** переменных. Как и в случае с функциями, не являющимися шаблонами, применяются преобразования стандартных типов (например, повышение переменной типа **`float`** до **`double`** ).

## <a name="example"></a>Пример

```cpp
// explicit_specialization.cpp
template<class T> void f(T t)
{
};

// Explicit specialization of f with 'char' with the
// template argument explicitly specified:
//
template<> void f<char>(char c)
{
}

// Explicit specialization of f with 'double' with the
// template argument deduced:
//
template<> void f(double d)
{
}
int main()
{
}
```

## <a name="see-also"></a>См. также раздел

[Шаблоны функций](../cpp/function-templates.md)
