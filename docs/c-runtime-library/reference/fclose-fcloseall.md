---
title: "fclose, _fcloseall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fclose"
  - "_fcloseall"
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
  - "fclose"
  - "_fcloseall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция fclose"
  - "потоки, закрытие"
  - "Функция _fcloseall"
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# fclose, _fcloseall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Закрывает поток \(`fclose`\) или закрывает все открытые потоки \(`_fcloseall`\).  
  
## Синтаксис  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 `fclose` возвращает 0, если поток успешно закрыт.  `_fcloseall` возвращает общее число закрытых потоков.  Обе функции возвращают `EOF` для указания ошибки.  
  
## Заметки  
 Функция `fclose` закрывает `stream`.  Если параметр `stream` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, то `fclose` устанавливает `errno` в `EINVAL` и возвращает `EOF`.  Рекомендуется, всегда проверять указатель `stream` до вызова этой функции.  
  
 См. раздел [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) для дополнительных сведений по этим и другим кодам возврата.  
  
 Функция `_fcloseall` закрывает все открытые потоки, кроме `stdin`, `stdout`, `stderr` \(и, в MS\-DOS, `_stdaux` и `_stdprn`\).  Она также закрывает и удаляет все временные файлы, созданные `tmpfile`.  В обеих функциях все буферы, связанные с потоком, сбрасываются до закрытия.  Размещенные системой буферы освобождаются, когда закрывается поток.  Буферы, назначенные пользователем с помощью функций `setbuf` и `setvbuf`, не освобождаются автоматически.  
  
 **Замечание:** Когда эти функции используются, чтобы закрыть поток, основной идентификатор файла и системный дескриптор файла \(или сокет\) закрываются, как и поток.  Таким образом, если файл был изначально открыт как дескриптор файла или идентификатор файла и закрыт с `fclose`, не следует дополнительно вызывать `_close`, чтобы закрыть идентификатор файла; не вызывайте функцию Win32 `CloseHandle`, чтобы закрыть дескриптор файла.  
  
 `fclose` и `_fcloseall` содержат код для защиты от влияния других потоков.  Для неблокирующей версии `fclose` см. `_fclose_nolock`.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`fclose`|\<stdio.h\>|  
|`_fcloseall`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## Эквивалент в .NET Framework  
  
-   [System::IO::BinaryReader::Close](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.close.aspx)  
  
-   [System::IO::BinaryWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.close.aspx)  
  
-   [System::IO::StringReader::Close](https://msdn.microsoft.com/en-us/library/system.io.stringreader.close.aspx)  
  
-   [System::IO::StringWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.stringwriter.close.aspx)  
  
-   [System::IO::Stream::Close](https://msdn.microsoft.com/en-us/library/system.io.stream.close.aspx)  
  
-   [System::IO::StreamReader::Close](https://msdn.microsoft.com/en-us/library/system.io.streamreader.close.aspx)  
  
-   [System::IO::StreamWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.close.aspx)  
  
-   [System::IO::TextReader::Close](https://msdn.microsoft.com/en-us/library/system.io.textreader.close.aspx)  
  
-   [System::IO::TextWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.textwriter.close.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [\_close](../Topic/_close.md)   
 [\_fdopen, \_wfdopen](../Topic/_fdopen,%20_wfdopen.md)   
 [fflush](../Topic/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)