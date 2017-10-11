---
title: "Выполните-while инструкции (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8c81bbeea9f841a834d59186017b2932f83de862
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="do-while-statement-c"></a>Выражение do-while (C++)
Выполняет *инструкции* пока указанное условие завершения ( *выражение*) будет равно нулю.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
do  
   statement  
while ( expression ) ;  
```  
  
## <a name="remarks"></a>Примечания  
 Проверка условия завершения выполняется после каждого выполнения цикла; поэтому цикл `do-while` выполняется один или несколько раз, в зависимости от значения выражения завершения. `do-while` Инструкция может также прерываться, когда [разрыв](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), или [возвращают](../cpp/return-statement-cpp.md) в теле оператора выполняется оператор.  
  
 Выражение *expression* должно иметь арифметический тип или тип указателя. Выполнение происходит следующим образом:  
  
1.  Выполняется тело оператора.  
  
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
 [Основанный на диапазоне оператор for (C++)](../cpp/range-based-for-statement-cpp.md)
