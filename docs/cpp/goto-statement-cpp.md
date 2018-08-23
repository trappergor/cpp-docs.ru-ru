---
title: Оператор GoTo (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- goto_cpp
dev_langs:
- C++
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38d022cb3b7f2672ffe7dba6a6d9d4952fa21616
ms.sourcegitcommit: 7f3df9ff0310a4716b8136ca20deba699ca86c6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2018
ms.locfileid: "42572123"
---
# <a name="goto-statement-c"></a>Оператор goto (C++)
**Goto** инструкции обеспечивает безусловную передачу управления оператору, метка которого задана идентификатором.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
goto identifier;  
```  
  
## <a name="remarks"></a>Примечания  
 Оператор, метка которого задана в параметре `identifier`, должен находиться в текущей функции. Все имена, заданные в параметре `identifier`, являются членами внутреннего пространства имен и, следовательно, не пересекаются с другими идентификаторами.  
  
 Метка оператора значима только для **goto** оператор; в противном случае метки операторов игнорируются. Повторное объявление меток невозможно.  

Объект **goto** инструкция является недопустимой для передачи управления в расположение, которая пропускает инициализацию любая переменная, которая находится в области в этом расположении. Приведенный ниже пример кода вызывает C2362:

```cpp
int goto_fn(bool b)
{
    if (!b)
    {
        goto exit;  // C2362
    }
    else
    { /*...*/ }

    int error_code = 42;

exit:
    return error_code;
}
```
  
 Это хороший стиль программирования **break**, **по-прежнему**, и **возвращают** инструкции вместо **goto** инструкции всякий раз, когда возможно. Тем не менее так как **break** инструкция завершает работу только из одного уровня цикла, может потребоваться использовать **goto** инструкции для выхода из глубоко вложенного цикла.  
  
 Дополнительные сведения о метках и **goto** инструкции, см. в разделе [операторы с метками](../cpp/labeled-statements.md).  
  
## <a name="example"></a>Пример  
 В этом примере **goto** оператор передает управление в точку с меткой `stop` при `i` равно 3.  
  
```cpp  
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
