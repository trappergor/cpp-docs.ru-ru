---
title: Предупреждение компилятора (уровень 1) C4533
ms.date: 11/04/2016
f1_keywords:
- C4533
helpviewer_keywords:
- C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
ms.openlocfilehash: 20637dc23e13031b4199298a3374825062ce40da
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186430"
---
# <a name="compiler-warning-level-1-c4533"></a>Предупреждение компилятора (уровень 1) C4533

Инициализация "Variable" пропускается "инструкцией"

Инструкция в программе изменила поток управления, таким, что инструкция, инициализирующая переменную, не была выполнена. Следующий пример приводит к возникновению ошибки C4533:

```cpp
// C4533.cpp
// compile with: /W1
#include <stdio.h>

struct A
{
   int m_data;
};

int main()
{
   if (1)
   {
      goto Label;
   }

   A a = { 100 };

   Label:   // C4533
      printf("\n%d", a.m_data);   // prints an uninitialized value
}
```
