---
title: "_chsize_s | Microsoft Docs"
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
  - "_chsize_s"
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
  - "chsize_s"
  - "_chsize_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chsize_s - функция"
  - "chsize_s - функция"
  - "файлы [C++], изменение размера"
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _chsize_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет размер файла.  Это версия [\_chsize](../../c-runtime-library/reference/chsize.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _chsize_s(   
   int fd,  
   __int64 size   
);  
```  
  
#### Параметры  
 `fd`  
 Идентификатор файла, ссылающийся на открытый файл.  
  
 `size`  
 Новая длина файла в байтах.  
  
## Возвращаемое значение  
 `_chsize_s` возвращает значение 0, если размер файла успешно изменен.  Возвращаемое ненулевое значение указывает на ошибку: возвращаемое значение равно `EACCES` , если указанный файл блокирован для доступа, `EBADF` , если указанный файл доступен только для чтения или дескриптор недопустим, `ENOSPC` , если отсутствует свободное место на устройстве, или `EINVAL` , если размер меньше нуля.  `errno` устанавливает в то же значение.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_chsize_s` расширяет или усекает файл, связанный с `fd`, до длины, указанной в `size`.  Файл должен быть открыт в режиме, который позволяет запись.  В файл добавляются нуль\-символы \('\\0'\), если файл расширяется.  Если файл усекается, все данные от конца сокращенного файла до длины исходного файла теряются.  
  
 `_chsize_s` принимает 64\-разрядное целое число в качестве размера файла, и поэтому может обрабатывать файлы, размер которых превосходит 4 ГБ.  `_chsize` ограничена 32\-разрядными размерами файлов.  
  
 Эта функция проверяет свои параметры.  Если `fd` не является допустимым идентификатором или размер файла меньше нуля, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_chsize_s`|\<io.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
  
-   [System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)  
  
-   [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../Topic/_close.md)   
 [Функция \_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)