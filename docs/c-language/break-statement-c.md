---
title: Оператор break в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- break
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 194e4c836f0423e20bb747cc6c3b06645c38a5fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381354"
---
# <a name="break-statement-c"></a>Оператор break (C)
Оператор `break` завершает выполнение ближайшего внешнего оператора `do`, `for`, `switch` или `while`, в котором он находится. Управление передается оператору, который расположен после завершенного оператора.  
  
## <a name="syntax"></a>Синтаксис  
 *оператор-перехода*:  
 `break;`  
  
 Оператор `break` часто используется для завершения обработки блока case, относящегося к оператору `switch`. Если внешний оператор итерации или оператор `switch` отсутствует, создается ошибка.  
  
 Если используются вложенные операторы, то `break` завершает выполнение только того оператора `do`, `for`, `switch` или `while`, который непосредственно его окружает. Передать управление за пределы вложенной структуры можно при помощи оператора `return` или `goto`.  
  
 В следующем примере показано использование оператора `break`:  
  
```  
#include <stdio.h>  
int main() {  
   char c;  
   for(;;) {  
      printf_s( "\nPress any key, Q to quit: " );  
  
      // Convert to character value  
      scanf_s("%c", &c);  
      if (c == 'Q')  
          break;  
   }  
} // Loop exits only when 'Q' is pressed  
```  
  
## <a name="see-also"></a>См. также  
 [Оператор break](../cpp/break-statement-cpp.md)