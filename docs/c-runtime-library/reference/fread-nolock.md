---
title: "_fread_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fread_nolock"
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
  - "_fread_nolock"
  - "fread_nolock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fread_nolock - функция"
  - "данные [C++], чтение из входящего потока"
  - "fread_nolock - функция"
  - "чтение данных [C++], из входящих потоков"
  - "потоки [C++], чтение данных из"
ms.assetid: 60e4958b-1097-46f5-a77b-94af5e7dba40
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _fread_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Считывает данные из потока, не блокируя другие потоки.  
  
## Синтаксис  
  
```  
size_t _fread_nolock(   
   void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### Параметры  
 `buffer`  
 Место хранения данных.  
  
 `size`  
 Размер элемента в байтах.  
  
 `count`  
 Максимальное количество элементов, которые требуется прочитать.  
  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 См. раздел [fread](../../c-runtime-library/reference/fread.md).  
  
## Заметки  
 Эта функция \- неблокирующая версия `fread`.  Она идентична `fread` за исключением того, что она не защищена от взаимодействия с другими потоками.  Она может выполняться быстрее, поскольку она не создают дополнительную нагрузку, связанную с блокировкой работы других потоков.  Эту функцию следует использовать только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_fread_nolock`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 [System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../Topic/fwrite.md)   
 [\_read](../Topic/_read.md)