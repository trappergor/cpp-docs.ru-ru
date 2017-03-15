---
title: "_unlock_file | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_unlock_file"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_unlock_file"
  - "unlock_file"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_unlock_file - функция"
  - "файлы [C++], разблокирование"
  - "unlock_file - функция"
  - "разблокирование файлов"
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _unlock_file
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Разблокирует файл, предоставляя другим процессам возможность доступа к файлу.  
  
## Синтаксис  
  
```  
void _unlock_file(  
   FILE* file  
);  
```  
  
#### Параметры  
 `file`  
 Дескриптор файла.  
  
## Заметки  
 Функция `_unlock_file` разблокирует файл, указанный в `file`.  Разблокирование файла предоставляет другим процессам возможность доступа к файлу.  Эта функция не должна вызываться, если `_lock_file` ранее не вызывалась с указателем `file`.  Вызов `_unlock_file` для незаблокированного файла может привести к блокировке процесса.  Пример см. в разделе [\_lock\_file](../Topic/_lock_file.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_unlock_file`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 [System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [Функция \_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_lock\_file](../Topic/_lock_file.md)