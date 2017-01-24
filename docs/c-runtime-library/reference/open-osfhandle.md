---
title: "_open_osfhandle | Microsoft Docs"
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
  - "_open_osfhandle"
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
  - "_open_osfhandle"
  - "open_osfhandle"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Функция open_osfhandle"
  - "дескрипторы файлов [C++], связывание"
  - "Функция _open_osfhandle"
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _open_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Связывает идентификатор файла С времени выполнения с существующим дескриптором файла операционной системы.  
  
## Синтаксис  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### Параметры  
 `osfhandle`  
 Дескриптор файла операционной системы.  
  
 `flags`  
 Типы допустимых операций.  
  
## Возвращаемое значение  
 В случае успеха `_open_osfhandle` возвращает идентификатор файла времени выполнения С.  В противном случае возвращается значение \-1.  
  
## Заметки  
 Функция `_open_osfhandle` выделяет идентификатор файла времени выполнения С и связывает его с дескриптором файла операционной системы `osfhandle`.  Аргумент `flags` — целочисленное выражение, построенное из одной или нескольких констант манифеста, определенных в Fcntl.h.  Если используется две или более константы манифеста для формирования аргумента `flags`, то константы объединяются с побитовым оператором OR \(  **&#124;** \).  
  
 Fcntl.h определяет следующие константы манифеста.  
  
 **\_O\_APPEND**  
 Перемещает указатель файла в конец файла перед каждой операцией записи.  
  
 **\_O\_RDONLY**  
 Открывает файл только для чтения.  
  
 **\_O\_TEXT**  
 Открывает файл в текстовом \(преобразованном\) режиме.  
  
 **\_O\_WTEXT**  
 Открывает файл в режиме Юникод \(преобразованном UTF\-16\).  
  
 Чтобы закрыть файл, открытый `_open_osfhandle`, вызовите `_close`.  Базовый дескриптор также можно закрыть вызовом `_close`, поэтому не нужно вызывать функцию `CloseHandle` Win32 для исходного дескриптора.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_open_osfhandle`|\<io.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 [System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)