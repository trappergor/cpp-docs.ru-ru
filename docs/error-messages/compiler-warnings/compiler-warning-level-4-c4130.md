---
title: Предупреждение (уровень 4) C4130 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4130
dev_langs:
- C++
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 226b715689e506cb34ea6e7684f9ddcf041e638b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4130"></a>Предупреждение компилятора (уровень 4) C4130
"оператор": логическая операция с адресом строковой константы  
  
 Использование оператора с адресом строкового литерала создает непредвиденный код.  
  
 Следующий пример приводит к возникновению ошибки C4130:  
  
```  
// C4130.cpp  
// compile with: /W4  
int main()  
{  
   char *pc;  
   pc = "Hello";  
   if (pc == "Hello") // C4130  
   {  
   }  
}  
```  
  
 Оператор **if** сравнивает значение, сохраненное в указателе `pc` на адрес строки "Hello", который выделяется отдельно каждый раз, когда строка встречается в коде. Оператор **if** не сравнивает строку, на которую указывает `pc` , со строкой "Hello".  
  
 Для сравнения строк используйте функцию `strcmp` .