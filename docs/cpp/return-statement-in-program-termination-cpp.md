---
title: Оператор Return при прерывании программы (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61d09c1b3aaea799c227686436486efa48fc7857
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="return-statement-in-program-termination-c"></a>Оператор return при прерывании программы (C++)
Выдача `return` инструкции от **основной** функционально эквивалентно вызову метода **выхода** функции. Рассмотрим следующий пример.  
  
```  
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 **Выхода** и `return` инструкции в предыдущем примере функционально идентичны. Однако C++ требует, чтобы функции, которые содержат типы возвращаемых значений, отличные от `void`, возвращали значение. `return` Инструкция позволяет возвращать значение из **основной**.  
  
## <a name="see-also"></a>См. также  
 [Завершение программы](../cpp/program-termination.md)