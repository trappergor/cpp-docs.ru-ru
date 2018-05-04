---
title: При использовании имен функций без () не создает никакого кода | Документы Microsoft
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
ms.openlocfilehash: 40aed3969ae0707b07f0912d7247b49886d0319d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="using-function-name-without--produces-no-code"></a>При использовании имен функций без скобок () код не создается
При использовании имени функции, объявленные в программе без скобок компилятор не создает код. Это происходит независимо от того, является ли функция принимает параметры, так как компилятор вычисляет адрес функции; Однако поскольку оператор вызова функции «()» не существует, вызов не происходит. Этот результат будет примерно следующим:  
  
```  
// compile with /Wall to generate a warning  
int a;  
a;      // no code generated here either  
```  
  
 В Visual C++ даже при использовании предупреждение уровня 4 создает выходные данные диагностики. Предупреждение не выдается; код не создается.  
  
 Следующий пример кода компилируется (с выводом предупреждения) и корректно компонуется без ошибок, но не создает никакого кода, ссылка на `funcn( )`. Чтобы это работало правильно добавьте оператор вызова функции «()».  
  
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