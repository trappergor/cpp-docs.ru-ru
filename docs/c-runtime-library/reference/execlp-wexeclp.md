---
title: "_execlp, _wexeclp | Microsoft Docs"
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
  - "_wexeclp"
  - "_execlp"
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
  - "_wexeclp"
  - "wexeclp"
  - "_execlp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_execlp - функция"
  - "_wexeclp - функция"
  - "execlp - функция"
  - "wexeclp - функция"
ms.assetid: 7b179163-4bcd-4d6a-8baf-68f886791928
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _execlp, _wexeclp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Загружает и выполняет новые дочерние процессы.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
intptr_t _execlp(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wexeclp(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### Параметры  
 `cmdname`  
 Путь к файлу для запуска.  
  
 `arg0`, `...``argn`  
 Список указателей на параметры.  
  
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
 Каждая из этих функций загружает и выполняет новый процесс, передавая каждый аргумент командной строки в виде отдельного параметра и используя переменную среды `PATH`, чтобы найти файл для выполнения.  
  
 Функции `_execlp` проверяют их параметры.  Если `cmdname` или `arg0` является указателем на null или пустой строкой, то эти функции вызывают обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1.  Нет запущенного нового процесса.  
  
## Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|-------------|----------------------------|------------------------------|  
|`_execlp`|\<process.h\>|\<errno.h\>|  
|`_wexeclp`|\<process.h\> или \<wchar.h\>|\<errno.h\>|  
  
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