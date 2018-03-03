---
title: "Оператор Return при прерывании программы (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a9e97c0ee52094cd3f0ccbb36c0da8b3b04c630
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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