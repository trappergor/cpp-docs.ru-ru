---
title: Ошибка компилятора C2385 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2385
dev_langs:
- C++
helpviewer_keywords:
- C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a52a932d45c94fb63f3d7b943b2cd78fa1862e4f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029056"
---
# <a name="compiler-error-c2385"></a>Ошибка компилятора C2385

неоднозначный уровень доступа «член»

Член может быть производным от более одного объекта (наследуется от более чем одного объекта).  Чтобы устранить эту ошибку,

- Сделать элемент, однозначны, предоставляя приведения к типу.

- Переименуйте неоднозначные члены в базовых классах.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2385.

```
// C2385.cpp
// C2385 expected
#include <stdio.h>

struct A
{
    void x(int i)
    {
        printf_s("\nIn A::x");
    }
};

struct B
{
    void x(char c)
    {
        printf_s("\nIn B::x");
    }
};

// Delete the following line to resolve.
struct C : A, B {}

// Uncomment the following 4 lines to resolve.
// struct C : A, B
// {
//     using B::x;
//     using A::x;
// };

int main()
{
    C aC;
    aC.x(100);
    aC.x('c');
}

struct C : A, B
{
    using B::x;
    using A::x;
};
```