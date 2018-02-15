---
title: "_alloca | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 104c3df4e6f69d31c5090a87c8029351accd1e1e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="alloca"></a>_alloca
Выделение памяти в стеке. Эта функция рекомендуется, поскольку существует более безопасная версия доступна; в разделе [_malloca](../../c-runtime-library/reference/malloca.md).  
  
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
 `_alloca` Выделяет `size` байтов из стека программы. Выделенное пространство освобождается автоматически при выходе из вызывающей функции, (не при распределении просто выйдет за пределы области). Таким образом, не передавайте значение указателя, возвращенное `_alloca` как аргумент [свободного](../../c-runtime-library/reference/free.md).  
  
 Существуют ограничения на явный вызов `_alloca` в обработчике исключений (EH). Подпрограммы обработки исключений, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции. Наиболее распространенные реализации включают выражения структурной обработки исключений (SEH) Windows NT и выражения catch языка C++. Поэтому явный вызов `_alloca` в любом из следующих сценариев приводит к сбою программы во время возврата к вызывающей подпрограмме EH:  
  
-   Выражение фильтрации исключений структурной обработки исключений Windows NT: `__except` (`_alloca ()`)  
  
-   Заключительный обработчик исключений структурной обработки исключений Windows NT: `__finally` {`_alloca ()`}  
  
-   Выражение catch обработки исключений языка C++  
  
 Однако `_alloca` можно вызывать непосредственно из подпрограммы обработки исключений или предоставленного приложением обратного вызова, который вызывается одним из перечисленных выше сценариев обработки исключений.  
  
> [!IMPORTANT]
>  В Windows XP, если `_alloca` вызывается внутри блока try/catch, необходимо вызвать метод [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) в блоке catch.  
  
 Помимо вышеуказанным ограничений при использовании[/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) параметр `_alloca` не может использоваться в `__except` блоков. Для получения дополнительной информации см. [/clr Restrictions](../../build/reference/clr-restrictions.md).  
  
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
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)