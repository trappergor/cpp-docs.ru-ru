---
title: При использовании имен функций без скобок () код не создается
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
ms.openlocfilehash: 51be77dc8f4fe072ea6cc46dd51e38862649feda
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827796"
---
# <a name="using-function-name-without--produces-no-code"></a>При использовании имен функций без скобок () код не создается

При использовании имени функции, объявленные в программе без скобок компилятор не создает код. Это происходит независимо от того, является ли функция принимает параметры, так как компилятор вычисляет адрес функции; Тем не менее потому что оператор вызова функции «()» отсутствует, вызов не происходит. Этот результат следующего вида:

```
// compile with /Wall to generate a warning
int a;
a;      // no code generated here either
```

В Visual C++ даже если используется уровень предупреждений 4 создает выходные данные диагностики. Предупреждение не выдается; код не создается.

Следующий пример кода компилируется (с предупреждением) и связывает правильно без ошибок, но не создает никакого кода к `funcn( )`. Чтобы это работало правильно добавьте оператор вызова функции «()».

```
#include <stdio.h>
void funcn();

int main() {
   funcn;      /* missing function call operator;
                  call will fail.  Use funcn() */
   }

void funcn() {
   printf("\nHello World\n");
}
```

## <a name="see-also"></a>См. также

[Оптимизация кода](optimizing-your-code.md)
