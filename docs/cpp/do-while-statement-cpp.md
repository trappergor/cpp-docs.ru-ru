---
title: Оператор do-while (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- do_cpp
dev_langs:
- C++
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e03a20ad2b49d5c9337e0c8250e5d7c321ee882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="do-while-statement-c"></a>Оператор do-while (C++)
Выполняет *statement* (инструкции) циклически, пока указанное условие завершения *expression* (выражение) не станет равно нулю. 
  
## <a name="syntax"></a>Синтаксис  
  
```  
do  
   statement  
while ( expression ) ;  
```  
  
## <a name="remarks"></a>Примечания  
 Проверка условия завершения выполняется после каждого выполнения тела цикла; поэтому цикл `do-while` выполняется один или несколько раз в зависимости от значения выражения завершения. Цикл `do-while` также может быть прерван, когда в его теле выполняется оператор [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md) или [return](../cpp/return-statement-cpp.md).  
  
 Выражение *expression* должно иметь арифметический тип или тип указателя. Выполнение происходит следующим образом:   
  
1.  Выполняется тело цикла.  
  
2.  Затем вычисляется значение *expression*. Если *expression* имеет значение false, выполнение оператора `do-while` завершается и управление передается следующему оператору программы. Если *expression* имеет значение true (то есть не равно нулю), процесс повторяется с шага 1. 
  
## <a name="example"></a>Пример  
 В следующем примере показано использование оператора `do-while`:  
  
```  
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Операторы итерации](../cpp/iteration-statements-cpp.md)    
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Оператор while (C++)](../cpp/while-statement-cpp.md)   
 [Оператор for (C++)](../cpp/for-statement-cpp.md)   
 [Оператор for для диапазона (C++)](../cpp/range-based-for-statement-cpp.md)
