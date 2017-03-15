---
title: "_fseek_nolock, _fseeki64_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fseek_nolock"
  - "_fseeki64_nolock"
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
  - "_fseek_nolock"
  - "_fseeki64_nolock"
  - "fseek_nolock"
  - "fseeki64_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fseek_nolock - функция"
  - "_fseeki64_nolock - функция"
  - "указатели файлов [C++], перемещение"
  - "fseek_nolock - функция"
  - "fseeki64_nolock - функция"
  - "искать указатели файлов"
ms.assetid: 2dd4022e-b715-462b-b935-837561605a02
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _fseek_nolock, _fseeki64_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Перемещает указатель файла в указанное местоположение.  
  
## Синтаксис  
  
```  
int _fseek_nolock(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64_nolock(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
 `offset`  
 Число байт, начиная с `origin.`  
  
 `origin`  
 Первоначальная позиция.  
  
## Возвращаемое значение  
 Аналогично [fseek, \_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md) соответственно.  
  
## Заметки  
 Эти функции являются неблокирующими версиями `fseek` и `_fseeki64` соответственно.          Эти функции совпадают с `fseek` и `_fseeki64` за исключением того, что они не защищены от вмешательства других потоков.  Эти функции могут выполняться быстрее, поскольку не создают дополнительную нагрузку, связанную с блокировкой работы других потоков.  Используйте эти функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`fseek`|\<stdio.h\>|  
|`_fseeki64`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
  
-   [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
-   [System::IO::FileStream::Seek](https://msdn.microsoft.com/en-us/library/system.io.filestream.seek.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)