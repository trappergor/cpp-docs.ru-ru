---
title: "_malloca | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_malloca"
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
  - "malloca"
  - "_malloca"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_malloca - функция"
  - "malloca - функция"
  - "выделение памяти, стек"
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _malloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделение памяти в стеке.  Это версия [\_alloca](../../c-runtime-library/reference/alloca.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### Параметры  
 `size`  
 Байты, которые нужно выделить из стека.  
  
## Возвращаемое значение  
 Процедура `_malloca` возвращает `void` указатель на выделенное место, которое гарантированно будет подходящим образом выравнено для хранения любого типа объекта.  Если значение `size` равно 0, `_malloca` выделяет элемент нулевой длины и возвращает допустимый указатель на этот элемент.  
  
 Исключение переполнения стека создается, если место не может быть выделено.  Исключение переполнения стека \- не исключение C\+\+; это структурированное исключение.  Вместо использования обработки исключений C\+\+, необходимо использовать [Структурную обработку исключений](../../cpp/structured-exception-handling-c-cpp.md) \(SEH\).  
  
## Заметки  
 `_malloca` выделяет `size` байтов из стека программы или кучи, если запрос превышает определенный размер в байтах, определяемый `_ALLOCA_S_THRESHOLD`.  Различие между `_malloca` и `_alloca` состоит в том, что `_alloca` всегда выделяет память из стека независимо от размера.  В отличие от `_alloca`, которая не требует или не позволяет вызывать `free` для освобождения памяти, выделенной таким образом, `_malloca` требует использования [\_freea](../../c-runtime-library/reference/freea.md) для освобождения памяти.  В режиме отладки `_malloca` всегда выделяет память из кучи.  
  
 Существуют ограничения для явного вызова `_malloca` в обработчике исключений \(EH\).  Процедуры EH, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: Они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции.  Наиболее распространенные реализации включают выражения структурной обработки исключений \(SEH\) Windows NT и условные выражения catch языка C\+\+.  Поэтому явный вызов `_malloca` в любом из следующих сценариев приводит к сбою программы во время возврата к вызывающей процедуре EH:  
  
-   Выражение фильтрации исключений структурной обработки исключений Windows NT: `__except` \(`_malloca ()` \)  
  
-   Заключительный обработчик исключений структурной обработки исключений Windows NT: `__finally` {`_malloca ()` }  
  
-   Условное выражение catch обработки исключений языка C\+\+  
  
 Однако `_malloca` можно вызывать непосредственно из процедуры EH или предоставленного приложением обратного вызова, который вызывается одним из перечисленных выше сценариев EH.  
  
> [!IMPORTANT]
>  В Windows XP, если `_malloca` вызывается внутри блока try\/catch, необходимо вызвать метод [\_resetstkoflw](../Topic/_resetstkoflw.md) в блоке catch.  
  
 Помимо вышеуказанным ограничений при использовании параметра [\/clr \(Компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md), `_malloca` нельзя использовать в блоках `__except`.  Дополнительные сведения см. в [Ограничения \/clr](../../build/reference/clr-restrictions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_malloca`|\<malloc.h\>|  
  
## Пример  
  
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
  
## Пример  
  
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
  
## Ввод  
  
```  
1000  
```  
  
## Пример результатов выполнения  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../Topic/_resetstkoflw.md)