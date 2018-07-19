---
title: Оператор Return при прерывании программы (C++) | Документация Майкрософт
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
ms.openlocfilehash: eb594eb10e8068d5f5b3ed124d5e77b48ced728e
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944164"
---
# <a name="return-statement-in-program-termination-c"></a>Оператор return при прерывании программы (C++)
Выдача `return` инструкции от **основной** является функционально эквивалентна вызову **выйти из** функции. Рассмотрим следующий пример.  
  
```cpp 
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 **Выйти из** и **возвращают** инструкции в предыдущем примере функционально идентичны. Однако C++ требует, что функции, которые имеют возвращать типы, отличные от **void** возвращают значение. **Возвращают** инструкция позволяет возвращать значение из `main`.  
  
## <a name="see-also"></a>См. также  
 [Завершение программы](../cpp/program-termination.md)