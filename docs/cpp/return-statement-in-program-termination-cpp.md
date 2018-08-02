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
ms.openlocfilehash: 6c08edff8237462cbc2c55dc5541e3da663ed0a3
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461117"
---
# <a name="return-statement-in-program-termination-c"></a>Оператор return при прерывании программы (C++)
Выдача **возвращают** инструкции от `main` является функционально эквивалентна вызову `exit` функции. Рассмотрим следующий пример.  
  
```cpp 
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 `exit` И **возвращают** инструкции в предыдущем примере функционально идентичны. Однако C++ требует, что функции, которые имеют возвращать типы, отличные от **void** возвращают значение. **Возвращают** инструкция позволяет возвращать значение из `main`.  
  
## <a name="see-also"></a>См. также  
 [Завершение программы](../cpp/program-termination.md)