---
title: Ошибка компилятора C2912
ms.date: 11/04/2016
f1_keywords:
- C2912
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
ms.openlocfilehash: 254252bfd21aa28c87810f1e21b4864e2775a71b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761089"
---
# <a name="compiler-error-c2912"></a>Ошибка компилятора C2912

явная специализация; declaration не является специализацией функции-шаблона

Невозможно специализировать нешаблонную функцию.

Следующий пример приводит к возникновению ошибки C2912:

```cpp
// C2912.cpp
// compile with: /c
void f(char);
template<> void f(char);   // C2912
template<class T> void f(T);   // OK
```

Эта ошибка может также возникать в результате изменений работы компилятора в Visual Studio .NET 2003: для каждой явной специализации необходимо выбрать параметры явной специализации так, чтобы они соответствовали параметрам первичного шаблона.

```cpp
// C2912b.cpp
class CF {
public:
   template <class A> CF(const A& a) {}   // primary template

   // attempted explicit specialization
   template <> CF(const char* p) {}   // C2912

   // try the following line instead
   // template <> CF(const char& p) {}
};
```
