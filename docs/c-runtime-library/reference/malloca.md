---
title: "_malloca | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _malloca
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
apitype: DLLExport
f1_keywords:
- malloca
- _malloca
dev_langs: C++
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcdeab9e61eda17164be06498e9ce42695faf8ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="malloca"></a>_malloca
Выделение памяти в стеке. Это версия функции [_alloca](../../c-runtime-library/reference/alloca.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `size`  
 Байты, которые нужно выделить из стека.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Подпрограмма `_malloca` возвращает указатель `void` на выделенное место, которое гарантированно будет подходящим образом выровнено для хранения объекта любого типа. Если значение `size` равно 0, `_malloca` выделяет элемент нулевой длины и возвращает допустимый указатель на этот элемент.  
  
 Если выделить место в памяти невозможно, создается исключение переполнения стека. Исключение переполнения стека не является исключением C++; это структурированное исключение. Вместо использования обработки исключений C++ необходимо использовать [структурированную обработку исключений](../../cpp/structured-exception-handling-c-cpp.md) (SEH).  
  
## <a name="remarks"></a>Примечания  
 `_malloca` выделяет `size` байтов из стека программы или кучи, если запрос превышает определенный размер в байтах, определяемый `_ALLOCA_S_THRESHOLD`. Различие между `_malloca` и `_alloca` состоит в том, что `_alloca` всегда выделяет память из стека независимо от размера. В отличие от функции `_alloca`, которая не требует или не позволяет вызывать `free` для освобождения памяти, выделенной таким образом, функция `_malloca` требует использования [_freea](../../c-runtime-library/reference/freea.md) для освобождения памяти. В режиме отладки `_malloca` всегда выделяет память из кучи.  
  
 Существуют ограничения на явный вызов `_malloca` в обработчике исключений (EH). Подпрограммы обработки исключений, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции. Наиболее распространенные реализации включают выражения структурной обработки исключений (SEH) Windows NT и выражения catch языка C++. Поэтому явный вызов `_malloca` в любом из следующих сценариев приводит к сбою программы во время возврата к вызывающей подпрограмме EH:  
  
-   Выражение фильтрации исключений структурной обработки исключений Windows NT: `__except` (`_malloca ()`)  
  
-   Заключительный обработчик исключений структурной обработки исключений Windows NT: `__finally` {`_malloca ()`}  
  
-   Выражение catch обработки исключений языка C++  
  
 Однако `_malloca` можно вызывать непосредственно из подпрограммы обработки исключений или предоставленного приложением обратного вызова, который вызывается одним из перечисленных выше сценариев обработки исключений.  
  
> [!IMPORTANT]
>  В Windows XP, если `_malloca` вызывается внутри блока try/catch, необходимо вызвать метод [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) в блоке catch.  
  
 Помимо вышеуказанных ограничений при использовании параметра [/clr (компиляция для среды CLR)](../../build/reference/clr-common-language-runtime-compilation.md), функцию `_malloca` нельзя использовать в блоках `__except`. Дополнительные сведения см. в разделе [Ограничения среды /clr](../../build/reference/clr-restrictions.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_malloca`|\<malloc.h>|  
  
## <a name="example"></a>Пример  
  
```  
// crt_malloca_simple.c  
#include <stdio.h>  
#include <malloc.h>  
  
void Fn()  
{  
   char * buf = (char *)_malloca( 100 );  
   // do something with buf  
   _freea( buf );  
}  
  
int main()  
{  
   Fn();  
}  
```  
  
## <a name="example"></a>Пример  
  
```  
// crt_malloca_exception.c  
// This program demonstrates the use of  
// _malloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size;  
    int     numberRead = 0;  
    int     errcode = 0;  
    void    *p = NULL;  
    void    *pMarker = NULL;  
  
    while (numberRead == 0)  
    {  
        printf_s("Enter the number of bytes to allocate "  
                 "using _malloca: ");  
        numberRead = scanf_s("%d", &size);  
    }  
  
    // Do not use try/catch for _malloca,  
    // use __try/__except, since _malloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try  
    {  
        if (size > 0)  
        {  
            p =  _malloca( size );  
        }  
        else  
        {  
            printf_s("Size must be a positive number.");  
        }  
        _freea( p );  
    }  
  
    // Catch any exceptions that may occur.  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_malloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf("Could not reset the stack!");  
            _exit(1);  
        }  
    };  
}  
```  
  
## <a name="input"></a>Входные данные  
  
```  
1000  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)