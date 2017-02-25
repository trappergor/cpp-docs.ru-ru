---
title: "_alloca | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_alloca"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_alloca"
  - "alloca"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_alloca - функция"
  - "alloca - функция"
  - "выделение памяти, стек"
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _alloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделение памяти в стеке.  Не рекомендуется использовать эту функцию, поскольку доступна более безопасная версия; см. [\_malloca](../../c-runtime-library/reference/malloca.md).  
  
## Синтаксис  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### Параметры  
 \[входящий\] `size`  
 Байты, которые нужно выделить из стека.  
  
## Возвращаемое значение  
 Процедура `_alloca` возвращает `void` указатель на выделенное место, которое гарантированно будет подходящим образом выравнено для хранения любого типа объекта.  Если значение `size` равно 0, `_alloca` выделяет элемент нулевой длины и возвращает допустимый указатель на этот элемент.  
  
 Исключение переполнения стека создается, если место не может быть выделено.  Исключение переполнения стека \- не исключение C\+\+; это структурированное исключение.  Вместо использования обработки исключений C\+\+, необходимо использовать [Структурную обработку исключений](../../cpp/structured-exception-handling-c-cpp.md) \(SEH\).  
  
## Заметки  
 `_alloca` выделяет `size` байтов из стека программы.  Выделенная память автоматически освобождается при выходе из вызывающей функции \(а не когда выделение выходит за пределы области\).  Поэтому не передавайте значение указателя, возвращенное `_alloca`, в качестве аргумента [free](../../c-runtime-library/reference/free.md).  
  
 Существуют ограничения для явного вызова `_alloca` в обработчике исключений \(EH\).  Процедуры EH, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: Они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции.  Наиболее распространенные реализации включают выражения структурной обработки исключений \(SEH\) Windows NT и условные выражения catch языка C\+\+.  Поэтому явный вызов `_alloca` в любом из следующих сценариев приводит к сбою программы во время возврата к вызывающей процедуре EH:  
  
-   Выражение фильтрации исключений структурной обработки исключений Windows NT: `__except` \(`_alloca ()` \)  
  
-   Заключительный обработчик исключений структурной обработки исключений Windows NT: `__finally` {`_alloca ()` }  
  
-   Условное выражение catch обработки исключений языка C\+\+  
  
 Однако `_alloca` можно вызывать непосредственно из процедуры EH или предоставленного приложением обратного вызова, который вызывается одним из перечисленных выше сценариев EH.  
  
> [!IMPORTANT]
>  В Windows XP, если `_alloca` вызывается внутри блока try\/catch, необходимо вызвать метод [\_resetstkoflw](../Topic/_resetstkoflw.md) в блоке catch.  
  
 Помимо вышеуказанных ограничений при использовании параметра [\/clr \(Common Language Runtime Compilation\)](../../build/reference/clr-common-language-runtime-compilation.md), `_alloca` нельзя использовать в блоках `__except`.  Дополнительные сведения см. в [Ограничения \/clr](../../build/reference/clr-restrictions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_alloca`|\<malloc.h\>|  
  
## Пример  
  
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
  
  **Allocated 1000 bytes of stack at 0x0012FB50**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../Topic/_resetstkoflw.md)   
 [\_malloca](../../c-runtime-library/reference/malloca.md)