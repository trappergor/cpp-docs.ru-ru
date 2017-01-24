---
title: "_execlpe, _wexeclpe | Microsoft Docs"
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
  - "_execlpe"
  - "_wexeclpe"
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
  - "_wexeclpe"
  - "execlpe"
  - "wexeclpe"
  - "_execlpe"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_execlpe - функция"
  - "_wexeclpe - функция"
  - "execlpe - функция"
  - "wexeclpe - функция"
ms.assetid: 07b861da-3e7e-4f1d-bb80-ad69b55e5162
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _execlpe, _wexeclpe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Загружает и выполняет новые дочерние процессы.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
intptr_t _execlpe(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wexeclpe(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL,  
   const wchar_t *const *envp   
);  
```  
  
#### Параметры  
 `cmdname`  
 Путь к файлу для запуска.  
  
 `arg0`, `...``argn`  
 Список указателей на параметры.  
  
 `envp`  
 Массив указателей на параметры среды.  
  
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
 Каждая из этих функций загружает и выполняет новый процесс, указав каждый аргумент командной строки как отдельный параметр, а также передает массив указателей на параметры среды.  Эти функции используют переменную среды `PATH` чтобы найти файл для выполнения.  
  
 Функции `_execlpe` проверяют их параметры.  Если `cmdname` или `arg0` указывают на null или пустую строку, то этими функциями вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1.  Нет запущенного нового процесса.  
  
## Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|-------------|----------------------------|------------------------------|  
|`_execlpe`|\<process.h\>|\<errno.h\>|  
|`_wexeclpe`|\<process.h\> или \<wchar.h\>|\<errno.h\>|  
  
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