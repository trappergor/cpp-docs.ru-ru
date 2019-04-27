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
ms.openlocfilehash: 3d91383f895f1a8be983efe42f685419ca988823
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184279"
---
# <a name="explicit-specialization-of-function-templates"></a>Явная специализация шаблонов функций

Используя шаблон функции, можно указать особое поведение для определенного типа, предоставив явную специализацию (переопределение) шаблона функции для этого типа. Пример:

```cpp
template<> void MySwap(double a, double b);
```

Это объявление позволяет определить другую функцию для **двойные** переменные. Подобно функциям не являющихся шаблонами, стандартные преобразования типов (например, преобразование типа **float** для **двойные**) применяются.

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

## <a name="see-also"></a>См. также

[Шаблоны функций](../cpp/function-templates.md)