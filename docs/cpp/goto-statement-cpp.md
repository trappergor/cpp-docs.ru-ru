---
title: "Перейти к инструкции (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- goto_cpp
dev_langs:
- C++
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3bdad97f36902762f34816a04a4fc0c5c0c16856
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="goto-statement-c"></a>Оператор goto (C++)
Оператор `goto` осуществляет безусловную передачу управления оператору, метка которого задана идентификатором.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
goto identifier;  
```  
  
## <a name="remarks"></a>Примечания  
 Оператор, метка которого задана в параметре `identifier`, должен находиться в текущей функции. Все имена, заданные в параметре `identifier`, являются членами внутреннего пространства имен и, следовательно, не пересекаются с другими идентификаторами.  
  
 Метка оператора имеет значение только для оператора `goto`; в остальных случаях метки операторов игнорируются. Повторное объявление меток невозможно.  
  
 Вместо `break` во всех случаях, когда это возможно, рекомендуется использовать операторы `continue`, `return` и `goto`. Однако, поскольку оператор `break` выполняет выход только из одного уровня цикла, возможны ситуации, когда для выхода из глубоко вложенного цикла может потребоваться использовать оператор `goto`.  
  
 Дополнительные сведения о метках и `goto` инструкции в разделе [операторы с метками](../cpp/labeled-statements.md) и [использование меток с оператором goto](http://msdn.microsoft.com/en-us/6cd7c31a-9822-4241-8566-f79f51be48fe).  
  
## <a name="example"></a>Пример  
 В этом примере оператор `goto` передает управление в точку с меткой `stop`, когда значение переменной `i` равно 3.  
  
```  
// goto_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 2; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 3 )  
                goto stop;  
        }  
    }  
  
    // This message does not print:   
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop:   
    printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
```Output  
Outer loop executing. i = 0  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 1  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 2  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 3  
 Inner loop executing. j = 0  
Jumped to stop. i = 3  
```  
  
## <a name="see-also"></a>См. также  
 [Операторы перехода](../cpp/jump-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
