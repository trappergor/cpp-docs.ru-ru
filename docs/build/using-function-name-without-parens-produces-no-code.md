---
title: При использовании имен функций без скобок () код не создается
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
ms.openlocfilehash: 51be77dc8f4fe072ea6cc46dd51e38862649feda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314602"
---
# <a name="using-function-name-without--produces-no-code"></a>При использовании имен функций без скобок () код не создается

Если использовать без круглых скобок имя функции, объявленное в программе, компилятор не создаст код. Это произойдет независимо от того, принимает ли функция параметры, поскольку компилятор рассчитывает адрес функции. Тем не менее, так как оператор вызова функции "()" отсутствует, вызов не выполняется. Результат будет выглядеть примерно так:

```
// compile with /Wall to generate a warning
int a;
a;      // no code generated here either
```

В Visual C++ даже при использовании уровня предупреждения 4 выходные данные диагностики не создаются. При этом не выдается предупреждение и не создается код.

Приведенный ниже пример кода успешно компилируется (с предупреждением) и компонуется без ошибок, однако при этом не создается код для `funcn( )`. Чтобы исправить этот код, необходимо добавить оператор вызова функции "()".

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
