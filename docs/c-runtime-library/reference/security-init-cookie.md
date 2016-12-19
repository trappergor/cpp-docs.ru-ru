---
title: "__security_init_cookie | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__security_init_cookie"
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
  - "security_init_cookie"
  - "__security_init_cookie"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__security_init_cookie - функция"
  - "файл cookie глобальной безопасности"
  - "файл cookie безопасности [C++]"
  - "security_init_cookie - функция"
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __security_init_cookie
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инициализирует глобальный cookie\-файл безопасности.  
  
## Синтаксис  
  
```  
void __security_init_cookie(void);  
```  
  
## Заметки  
 Глобальный cookie\-файл безопасности используется для защиты от переполнения буфера в коде, скомпилированном с параметром [Параметр \/GS \(проверка безопасности буфера\)](../Topic/-GS%20\(Buffer%20Security%20Check\).md), и в коде, в котором используется структурная обработка исключений.  При входе в функцию с защитой от переполнения cookie\-файл помещается в стек, а при выходе значение в стеке сравнивается с глобальным cookie\-файлом.  Любое различие между ними указывает, что произошло переполнение буфера, что приводит к немедленному завершению работы программы.  
  
 Обычно CRT вызывает `__security_init_cookie` при инициализации.  Если пропустить инициализацию CRT, например, если используется [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) для указания точки ввода, то нужно вызвать `__security_init_cookie` вручную.  Если не вызвать `__security_init_cookie`, то для глобального cookie\-файла безопасности устанавливается значение по умолчанию и нарушается защита от переполнения буфера.  Злоумышленник может воспользоваться этим значением cookie\-файла по умолчанию, чтобы обойти проверку переполнения буфера, поэтому рекомендуется всегда вызывать `__security_init_cookie` при определении собственной точки входа.  
  
 Функцию `__security_init_cookie` необходимо вызывать до входа в любую функцию, защищенную от переполнения; в противном случае будет обнаружено ложное переполнение буфера.  Для получения дополнительной информации см. [Ошибка во время выполнения C R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## Пример  
 См. примеры в разделе [Ошибка во время выполнения C R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`__security_init_cookie`|\<process.h\>|  
  
 `__security_init_cookie` — расширение Майкрософт для стандартной библиотеки выполнения C.  Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Эту функцию следует вызывать только из собственного кода, но не из управляемого кода.  
  
## См. также  
 [Подробно о проверках безопасности компилятора](http://go.microsoft.com/fwlink/?linkid=7260)