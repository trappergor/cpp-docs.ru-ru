---
title: "_get_invalid_parameter_handler _get_thread_local_invalid_parameter_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_invalid_parameter_handler"
  - "_get_thread_local_invalid_parameter_handler"
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
  - "_get_invalid_parameter_handler"
  - "stdlib/_get_invalid_parameter_handler"
  - "_get_thread_local_invalid_parameter_handler"
  - "stdlib/_get_thread_local_invalid_parameter_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функция _get_thread_local_invalid_parameter_handler"
  - "функция _get_invalid_parameter_handler"
ms.assetid: a176da0e-38ca-4d99-92bb-b0e2b8072f53
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# _get_invalid_parameter_handler _get_thread_local_invalid_parameter_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает функцию, которая вызывается, когда CRT обнаруживает недопустимый аргумент.  
  
## Синтаксис  
  
```  
_invalid_parameter_handler _get_invalid_parameter_handler(void);  
_invalid_parameter_handler _get_thread_local_invalid_parameter_handler(void);  
```  
  
## Возвращаемое значение  
 Указатель на текущее функция обработчика недопустимого параметра или указатель null, если ни один не задана.  
  
## Заметки  
 `_get_invalid_parameter_handler` Функция возвращает текущее обработчик глобального недопустимого параметра. Он возвращает указатель null, если обработчик глобального недопустимый параметр не задан. Аналогичным образом `_get_thread_local_invalid_parameter_handler` возвращает текущий обработчик недопустимого параметра локального потока он вызывается для потока, или указатель null, если обработчик не был задан. Сведения о том, как задать обработчики глобальной и локальной неправильный параметр в разделе [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).  
  
 Указатель на функцию обработчика недопустимого параметра, возвращенного имеет следующий тип:  
  
```c  
typedef void (__cdecl* _invalid_parameter_handler)(  
    wchar_t const*,  
    wchar_t const*,  
    wchar_t const*,   
    unsigned int,  
    uintptr_t  
    );  
```  
  
 Подробнее о обработчик недопустимого параметра, в разделе прототип в [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_invalid_parameter_handler`, `_get_thread_local_invalid_parameter_handler`|C: \< stdlib.h \><br /><br /> C\+\+: \< cstdlib \> или \< stdlib.h \>|  
  
 `_get_invalid_parameter_handler` И `_get_thread_local_invalid_parameter_handler` функции, определенные Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)   
 [Версии функций CRT повышенной безопасности](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)