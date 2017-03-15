---
title: "_set_invalid_parameter_handler _set_thread_local_invalid_parameter_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_invalid_parameter_handler"
  - "_set_invalid_parameter_handler"
  - "_set_thread_local_invalid_parameter_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработчик недопустимого параметра"
  - "set_invalid_parameter_handler - функция"
  - "_set_invalid_parameter_handler - функция"
  - "функция _set_thread_local_invalid_parameter_handler"
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _set_invalid_parameter_handler _set_thread_local_invalid_parameter_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Устанавливает функцию для вызова, когда CRT обнаруживает недопустимый аргумент.  
  
## Синтаксис  
  
```  
_invalid_parameter_handler _set_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(  
   _invalid_parameter_handler pNew  
);  
```  
  
#### Параметры  
 \[in\] `pNew`  
 Указатель на функцию нового обработчика недопустимого параметра.  
  
## Возвращаемое значение  
 Указатель на обработчик недопустимого параметра до вызова.  
  
## Заметки  
 Многие функции времени выполнения C проверяют допустимость аргументов, передаваемых в них. Если передается недопустимый аргумент, функция может установить номер ошибки `errno` или вернуть код ошибки. В таких случаях также вызывается обработчик недопустимого параметра. Среда выполнения C предоставляет обработчик по умолчанию глобальные недопустимого параметра, завершает программу и отображает сообщение об ошибке времени выполнения. Можно использовать `_set_invalid_parameter_handler` чтобы задать собственную функцию как обработчик глобального недопустимого параметра. Среда выполнения C также поддерживает обработчик недопустимого параметра локального потока. Если обработчик параметра локального потока в поток задается с помощью `_set_thread_local_invalid_parameter_handler`, функции времени выполнения C, вызывается из потока использовать этот обработчик вместо глобального обработчика. Только одна функция можно указать в качестве глобального недопустимый аргумент обработчика одновременно. Только одну функцию можно указать как обработчик локального потока недопустимый аргумент для каждого потока, но различными потоками может иметь различные обработчики локального потока. Это позволяет изменить обработчик, который используется в одной части кода, не влияющий на поведение других потоков.  
  
 Когда среда выполнения вызывает функцию обработки недопустимого параметра, это обычно означает, что произошла неустранимая ошибка. Функция обработчика недопустимого параметра, которые вводятся следует сохранять данные, его можно и затем прерваться. Она не должна возвращать управление функции main, если вы не уверены, что ошибка исправима.  
  
 Функция обработчика недопустимого параметра должна иметь следующий прототип:  
  
```c  
void _invalid_parameter(  
   const wchar_t * expression,  
   const wchar_t * function,   
   const wchar_t * file,   
   unsigned int line,  
   uintptr_t pReserved  
);  
```  
  
 `expression` Аргумент представляет собой двухбайтового строкового выражения аргумента, вызвавшего ошибку.`function` Аргумент — имя функции CRT, которая получила недопустимый аргумент.`file` Аргумент — имя исходного файла CRT, содержащего функцию.`line` Аргумент — это номер строки в этом файле. Последний аргумент зарезервирован. Все параметры имеют значение `NULL`, если не используется отладочная версия библиотеки CRT.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_set_invalid_parameter_handler`, `_set_thread_local_invalid_parameter_handler`|C: \< stdlib.h \><br /><br /> C\+\+: \< cstdlib \> или \< stdlib.h \>|  
  
 `_set_invalid_parameter_handler` И `_set_thread_local_invalid_parameter_handler` функции, определенные Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 В следующем примере обработчик ошибок недопустимого параметра используется для печати функции, которая получила недопустимый параметр, и файла и строки в источниках CRT. При использовании библиотеки отладки CRT, ошибки недопустимого параметра также вызывают утверждение, которое отключено в этом примере с помощью [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md).  
  
```c  
// crt_set_invalid_parameter_handler.c  
// compile with: /Zi /MTd  
#include <stdio.h>  
#include <stdlib.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
  
void myInvalidParameterHandler(const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter detected in function %s."  
            L" File: %s Line: %d\n", function, file, line);  
   wprintf(L"Expression: %s\n", expression);  
   abort();  
}  
  
int main( )  
{  
   char* formatString;  
  
   _invalid_parameter_handler oldHandler, newHandler;  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   // Call printf_s with invalid parameters.  
  
   formatString = NULL;  
   printf(formatString);  
}  
```  
  
```Output  
Обнаружено неверное значение параметра в функции common_vfprintf. Файл: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp строки: 32 выражения: формат! = nullptr  
```  
  
## См. также  
 [\_get\_invalid\_parameter\_handler \_get\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)   
 [Версии функций CRT повышенной безопасности](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)   
 [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)