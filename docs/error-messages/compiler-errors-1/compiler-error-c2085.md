---
title: Ошибка компилятора C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: a65e3c0ea622950b99b9ba83fc168b4718d13e46
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560164"
---
# <a name="compiler-error-c2085"></a>Ошибка компилятора C2085

«Идентификатор»: не в списке формальных параметров

Идентификатор был объявлен в определении функции, но не в списке формальных параметров. (Только в ANSI C)

Следующий пример приводит к возникновению ошибки C2085:

```
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

Возможное решение

```
// C2085b.c
void func1( void );
int main( void ) {}
```

С помощью отсутствует точка с запятой, `func1()` выглядит как определение функции, а не как прототип, поэтому `main` определяется внутри `func1()`, ошибки C2085 для идентификатора `main`.