---
title: Ошибка компилятора C2993
ms.date: 11/04/2016
f1_keywords:
- C2993
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
ms.openlocfilehash: 5aa0d27b2d469f53ec521f587172398b7d4c2d1b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761235"
---
# <a name="compiler-error-c2993"></a>Ошибка компилятора C2993

"идентификатор": недопустимый тип для параметра шаблона "параметр", не являющегося типом

Нельзя объявить шаблон с аргументом Structure или Union. Используйте указатели для передачи структур и объединений в качестве параметров шаблона.

Следующий пример приводит к возникновению ошибки C2993:

```cpp
// C2993.cpp
// compile with: /c
// C2993 expected
struct MyStruct {
   int a;char b;
};

template <class T, struct MyStruct S>   // C2993

// try the following line instead
// template <class T, struct MyStruct * S>
class CMyClass {};
```

Эта ошибка также будет сформирована в результате работы по согласованности компилятора, выполненной в Visual Studio .NET 2003: параметры шаблона с плавающей запятой, не являющиеся типами, больше не допускаются. C++ Стандарт не допускает параметры шаблона, не являющиеся типами с плавающей запятой.

Если это шаблон функции, используйте аргумент функции для передачи параметра шаблона, не являющегося типом с плавающей запятой (этот код будет действительным в Visual Studio .NET 2003 и Visual Studio .NET версии Visual C++). Если это шаблон класса, простого решения не существует.

```cpp
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```
