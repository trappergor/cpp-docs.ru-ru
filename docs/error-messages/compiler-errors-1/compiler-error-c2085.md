---
title: Ошибка компилятора C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: 7dbf7266a6330a1fdb46d7f2df90e7684f026d9a
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301968"
---
# <a name="compiler-error-c2085"></a>Ошибка компилятора C2085

"идентификатор": отсутствует в списке формальных параметров

Идентификатор был объявлен в определении функции, но отсутствует в списке формальных параметров. (Только ANSI C)

Следующий пример приводит к возникновению ошибки C2085:

```c
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

Возможное решение:

```c
// C2085b.c
void func1( void );
int main( void ) {}
```

Если точка с запятой отсутствует, `func1()` выглядит как определение функции, а не прототип, поэтому `main` определяется в `func1()`, создавая ошибку C2085 для идентификатора `main`.
