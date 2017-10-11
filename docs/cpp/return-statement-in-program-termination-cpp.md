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
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: f5ba078ef364a046a9e635d8b2632558e426f4b8
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

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
