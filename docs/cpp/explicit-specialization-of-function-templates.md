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
ms.openlocfilehash: c9d77cef790bdd0a65651ffb7246e685175482b1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179995"
---
# <a name="explicit-specialization-of-function-templates"></a>Явная специализация шаблонов функций

Используя шаблон функции, можно указать особое поведение для определенного типа, предоставив явную специализацию (переопределение) шаблона функции для этого типа. Пример:

```cpp
template<> void MySwap(double a, double b);
```

Это объявление позволяет определить другую функцию для переменных **типа Double** . Как и в случае с функциями, не являющимися шаблонами, применяются преобразования стандартных типов (например, повышение переменной типа **float** на **Double**).

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
