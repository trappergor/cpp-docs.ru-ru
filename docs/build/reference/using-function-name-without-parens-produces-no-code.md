---
title: При использовании имен функций без () код не создается | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13ca43386c9ef46f526538781a91fd1a81ade537
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710584"
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

[Оптимизация кода](../../build/reference/optimizing-your-code.md)