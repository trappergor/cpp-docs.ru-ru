---
title: "_alloca | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _alloca
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
- _alloca
- alloca
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: c7bf8e09b7af4153bae3bfa0f80c002149ff3ee9
ms.lasthandoff: 02/24/2017

---
# <a name="alloca"></a>_alloca
Выделение памяти в стеке. Эта функция устарела, так как доступно более безопасные версии; в разделе [_malloca](../../c-runtime-library/reference/malloca.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `size`  
 Байты, которые нужно выделить из стека.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Подпрограмма `_alloca` возвращает указатель `void` на выделенное место, которое гарантированно будет подходящим образом выровнено для хранения объекта любого типа. Если значение `size` равно 0, `_alloca` выделяет элемент нулевой длины и возвращает допустимый указатель на этот элемент.  
  
 Если выделить место в памяти невозможно, создается исключение переполнения стека. Исключение переполнения стека не является исключением C++; это структурированное исключение. Вместо использования обработки исключений C++ необходимо использовать [структурированную обработку исключений](../../cpp/structured-exception-handling-c-cpp.md) (SEH).  
  
## <a name="remarks"></a>Примечания  
 `_alloca`Выделяет `size` байтов из стека программы. Место, выделяемое автоматически освобождается при выходе из вызывающей функции, (не при выделении просто выйдет за пределы области). Таким образом, не следует передавать значение указателя, возвращенное `_alloca` в качестве аргумента [свободного](../../c-runtime-library/reference/free.md).  
  
 Существуют ограничения на явный вызов `_alloca` в обработчике исключений (EH). Подпрограммы обработки исключений, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции. Наиболее распространенные реализации включают выражения структурной обработки исключений (SEH) Windows NT и выражения catch языка C++. Поэтому явный вызов `_alloca` в любом из следующих сценариев приводит к сбою программы во время возврата к вызывающей подпрограмме EH:  
  
-   Выражение фильтрации исключений структурной обработки исключений Windows NT: `__except` (`_alloca ()`)  
  
-   Заключительный обработчик исключений структурной обработки исключений Windows NT: `__finally` {`_alloca ()`}  
  
-   Выражение catch обработки исключений языка C++  
  
 Однако `_alloca` можно вызывать непосредственно из подпрограммы обработки исключений или предоставленного приложением обратного вызова, который вызывается одним из перечисленных выше сценариев обработки исключений.  
  
> [!IMPORTANT]
>  В Windows XP, если `_alloca` вызывается внутри блока try/catch, необходимо вызвать метод [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) в блоке catch.  
  
 Помимо вышеуказанным ограничений при использовании[/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) параметр, `_alloca` не может использоваться в `__except` блоков. Дополнительные сведения см. в разделе [Ограничения среды /clr](../../build/reference/clr-restrictions.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_alloca`|\<malloc.h>|  
  
## <a name="example"></a>Пример  
  
```  
// crt_alloca.c  
// This program demonstrates the use of  
// _alloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size = 1000;  
    int     errcode = 0;  
    void    *pData = NULL;  
  
    // Note: Do not use try/catch for _alloca,  
    // use __try/__except, since _alloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try {  
        // An unbounded _alloca can easily result in a   
        // stack overflow.  
        // Checking for a size < 1024 bytes is recommended.  
        if (size > 0 && size < 1024)  
        {  
            pData = _alloca( size );  
            printf_s( "Allocated %d bytes of stack at 0x%p",  
                      size, pData);  
        }  
        else  
        {  
            printf_s("Tried to allocate too many bytes.\n");  
        }  
    }  
  
    // If an exception occured with the _alloca function  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_alloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf_s("Could not reset the stack!\n");  
            _exit(1);  
        }  
    };  
}  
```  
  
```Output  
Allocated 1000 bytes of stack at 0x0012FB50  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)
