---
title: Компилятор предупреждение (уровень 3) C4197
ms.date: 11/04/2016
f1_keywords:
- C4197
helpviewer_keywords:
- C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
ms.openlocfilehash: 15b2fba94bfc956775a1e454893e7509a32000e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402246"
---
# <a name="compiler-warning-level-3-c4197"></a>Компилятор предупреждение (уровень 3) C4197

«Тип»: входящее приведение volatile верхнего уровня игнорируется

Компилятор обнаружил приведения к типу значения, который определен с помощью [volatile](../../cpp/volatile-cpp.md), или преобразование типа значения к такому типу, который дополнены volatile. В соответствии со стандартом C (6.5.3) свойства, связанные с определенными типами имеют смысл только для выражения l значением.

Следующий пример приводит к возникновению ошибки C4197:

```
// C4197.cpp
// compile with: /W3
#include <stdio.h>
#include <signal.h>
#include <stdlib.h>

void sigproc(int);
struct S
{
   int i;
} s;

int main()
{
   signal(SIGINT, sigproc);
   s.i = 1;
   S *pS = &s;
   for ( ; (volatile int)pS->i ; )   // C4197
      break;
   // for ( ; *(volatile int *)&pS->i ; )   // OK
   //    break;
}

void sigproc(int) // ctrl-C
{
   signal(SIGINT, sigproc);
   s.i = 0;
}
```