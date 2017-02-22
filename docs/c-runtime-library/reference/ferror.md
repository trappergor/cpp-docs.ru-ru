---
title: "ferror | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ferror"
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
  - "ferror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ошибки [C++], проверка для потока"
  - "ferror - функция"
  - "потоки, проверка на наличие ошибок"
ms.assetid: 528a34bc-f2aa-4c3f-b89a-5b148e6864f7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# ferror
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет на ошибки в потоке.  
  
## Синтаксис  
  
```  
int ferror(   
   FILE *stream   
);  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 Если ошибок в `stream` нет, `ferror` возвращает 0.  В противном случае возвращается ненулевое значение.  Если поток `NULL`, то `ferror` вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция устанавливает `errno` в значение `EINVAL` и возвращает 0.  
  
 См. раздел [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для дополнительных сведений по этим и другим кодам возврата.  
  
## Заметки  
 Процедура `ferror` \(реализованная и как функция, и как макрос\) проверяет наличие ошибок чтения или записи в файле, связанном с `stream`.  Если произошла ошибка, индикатор ошибки для потока остается установленным до тех пор, пока поток не закрыт или перемотан назад или пока не вызвана функция `clearerr` для потока.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`ferror`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [feof](../../c-runtime-library/reference/feof.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Обработка ошибок](../../c-runtime-library/error-handling-crt.md)   
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [\_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)