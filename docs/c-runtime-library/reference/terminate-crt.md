---
title: "terminate (CRT) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- terminate
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- terminate
dev_langs:
- C++
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0be18926e565604e2985b0e3afed571b752465b7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="terminate-crt"></a>terminate (CRT)
Вызывает функцию `abort` или функцию, заданную с помощью `set_terminate`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void terminate( void );  
```  
  
## <a name="remarks"></a>Примечания  
 Функция `terminate` используется с обработкой исключений C++ и вызывается в следующих случаях:  
  
-   не удается найти подходящий обработчик catch для исключения C++;  
  
-   исключение создано деструктором во время очистки стека;  
  
-   стек поврежден после возникновения исключения.  
  
 По умолчанию `terminate` вызывает функцию `abort`. Это поведение по умолчанию можно изменить, создав собственную функцию завершения и вызвав функцию `set_terminate` с именем этой функции в качестве аргумента. `terminate` вызывает последнюю функцию, заданную в качестве аргумента для функции `set_terminate`. Дополнительные сведения см. в разделе [Необработанные исключения C++](../../cpp/unhandled-cpp-exceptions.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`terminate`|\<eh.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_terminate.cpp  
// compile with: /EHsc  
#include <eh.h>  
#include <process.h>  
#include <iostream>  
using namespace std;  
  
void term_func();  
  
int main()  
{  
    int i = 10, j = 0, result;  
    set_terminate( term_func );  
    try  
    {  
        if( j == 0 )  
            throw "Divide by zero!";  
        else  
            result = i/j;  
    }  
    catch( int )  
    {  
        cout << "Caught some integer exception.\n";  
    }  
    cout << "This should never print.\n";  
}  
  
void term_func()  
{  
    cout << "term_func() was called by terminate().\n";  
  
    // ... cleanup tasks performed here  
  
    // If this function does not exit, abort is called.  
  
    exit(-1);  
}  
```  
  
```Output  
term_func() was called by terminate().  
```  
  
## <a name="see-also"></a>См. также  
 [Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)