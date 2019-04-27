---
title: Ошибка компилятора C2764
ms.date: 11/04/2016
f1_keywords:
- C2764
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
ms.openlocfilehash: ba16431fc71a0e594b77dcc6dab62ed6c49c9137
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257495"
---
# <a name="compiler-error-c2764"></a>Ошибка компилятора C2764

«параметр»: параметр шаблона не используется или не выводится в частичной специализации «специализация»

Параметр шаблона в частичной специализации не используется. В результате частичной специализации невозможно использовать, так как параметр шаблона не может быть выведен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2764:

```
// C2764.cpp
#include <stdio.h>
template <class T1, class T2>
struct S  {
   int m_i;
};

template <class T1, class T2>
struct S<int, T2*> {   // C2764
// try the following line instead
// struct S<T1(*)(T2), T2*> {
   char m_c;
};

int main() {
   S<int, char> s1;
   S<void (*)(short), short *> s2;
   s2.m_c = 10;
   s1.m_i = s2.m_c;
   printf_s("%d\n", s1.m_i);
}
```