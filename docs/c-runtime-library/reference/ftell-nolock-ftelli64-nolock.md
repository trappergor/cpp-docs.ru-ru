---
title: "_ftell_nolock, _ftelli64_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ftelli64_nolock"
  - "_ftell_nolock"
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
  - "_ftelli64_nolock"
  - "ftelli64_nolock"
  - "ftell_nolock"
  - "_ftell_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftell_nolock - функция"
  - "_ftelli64_nolock - функция"
  - "указатели файлов [C++], получение текущей позиции"
  - "ftell_nolock - функция"
  - "ftelli64_nolock - функция"
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _ftell_nolock, _ftelli64_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает текущее положение указателя файла без блокирования потока.  
  
## Синтаксис  
  
```  
long _ftell_nolock(   
   FILE *stream   
);  
__int64 _ftelli64_nolock(   
   FILE *stream   
);  
```  
  
#### Параметры  
 `stream`  
 Цель — структура `FILE`.  
  
## Возвращаемое значение  
 Аналогично `ftell` и `_ftelli64`.  Дополнительные сведения см. в разделе [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md).  
  
## Заметки  
 Эти функции являются неблокирующими версиями `ftell` и `_ftelli64` соответственно.  Эти функции совпадают с `ftell` и `_ftelli64`за исключением того, что они не защищены от вмешательства других потоков.  Эти функции могут выполняться быстрее, поскольку не создают дополнительную нагрузку, связанную с блокировкой работы других потоков.  Используйте эти функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.  
  
## Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|-------------|----------------------------|------------------------------|  
|`ftell_nolock`|\<stdio.h\>|\<errno.h\>|  
|`_ftelli64_nolock`|\<stdio.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)