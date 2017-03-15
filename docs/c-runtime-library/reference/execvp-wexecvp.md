---
title: "_execvp, _wexecvp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_execvp"
  - "_wexecvp"
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
  - "api-ms-win-crt-process-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_execvp"
  - "wexecvp"
  - "_wexecvp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_execvp - функция"
  - "_wexecvp - функция"
  - "execvp - функция"
  - "wexecvp - функция"
ms.assetid: a4db15df-b204-4987-be7c-de84c3414380
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _execvp, _wexecvp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Загружает и выполняет новые дочерние процессы.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
intptr_t _execvp(   
   const char *cmdname,  
   const char *const *argv   
);  
intptr_t _wexecvp(   
   const wchar_t *cmdname,  
   const wchar_t *const *argv   
);  
```  
  
#### Параметры  
 `cmdname`  
 Путь к файлу для запуска.  
  
 `argv`  
 Массив указателей на параметры.  
  
## Возвращаемое значение  
 Если успешно, эти функции не возвращают вызывающему процессу.  Возвращаемое значение –1 означает ошибку, в соответствии с которой устанавливается глобальная переменная `errno`.  
  
|Значение `errno`|Описание|  
|----------------------|--------------|  
|`E2BIG`|Требуемое место для аргументов и параметров среды превышает 32 КБ.|  
|`EACCES`|Указанный файл имеет блокировку или нарушение совместного использования.|  
|`EINVAL`|Неверный параметр|  
|`EMFILE`|Слишком много открытых файлов \(указанный файл должен быть открыт чтобы определить, является ли он исполняемым\).|  
|`ENOENT`|Не найден файл или путь.|  
|`ENOEXEC`|Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.|  
|`ENOMEM`|Недостаточно памяти для выполнения нового процесса; доступная память была повреждена;существует недопустимый блок, показывающий, что вызывающий процесс не был правильно размещен.|  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Каждая из этих функций загружает и выполняет новый процесс, передавая массив указателей на аргументы командной строки и используя переменную среды `PATH`, чтобы найти файл для выполнения.  
  
 Функции `_execvp` проверяют их параметры.  Если `cmdname` является пустым указателем, или если `argv` является пустым указателем, указателем на пустой массив, или если массив содержит пустую строку в качестве первого аргумента, то эти функции вызывают обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1.  Ни один процесс не запущен.  
  
## Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|-------------|----------------------------|------------------------------|  
|`_execvp`|\<process.h\>|\<errno.h\>|  
|`_wexecvp`|\<process.h\> или \<wchar.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример в [Функции \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md).  
  
## Эквивалент в .NET Framework  
  
-   [Класс System::Diagnostics::Process](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [Класс System::Diagnostics::ProcessStartInfo](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)