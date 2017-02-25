---
title: "_get_printf_count_output | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_printf_count_output"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_printf_count_output"
  - "_get_printf_count_output"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%n - формат"
  - "_get_printf_count_output - функция"
  - "get_printf_count_output - функция"
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _get_printf_count_output
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, поддерживает ли семейство функций [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) формат `%n`.  
  
## Синтаксис  
  
```  
int _get_printf_count_output();  
```  
  
## Возвращаемое значение  
 Ненулевое значение, если `%n` поддерживается, 0, если `%n` не поддерживается.  
  
## Заметки  
 Если `%n` не поддерживается \(по умолчанию\), то возникновение `%n` в строке формата любых функций `printf` вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если поддержка `%n` включена \(см. в разделе [\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md)\), то `%n` будет работать, как описано в разделе [Символы поля типа printf](../../c-runtime-library/printf-type-field-characters.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_printf_count_output`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример в разделе [\_set\_printf\_count\_output](../../c-runtime-library/reference/set-printf-count-output.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).