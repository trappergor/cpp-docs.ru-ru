---
title: "_execle, _wexecle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_execle"
  - "_wexecle"
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
  - "wexecle"
  - "_execle"
  - "_wexecle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_execle - функция"
  - "_wexecle - функция"
  - "execle - функция"
  - "wexecle - функция"
ms.assetid: 75efa9c5-96b7-4e23-acab-06258901f63a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _execle, _wexecle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Загружает и выполняет новые дочерние процессы.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
intptr_t _execle(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL,  
   const char *const *envp   
);  
intptr_t _wexecle(   
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL,  
   const char *const *envp   
);  
```  
  
#### Параметры  
 `cmdname`  
 Путь к выполняемому файлу.  
  
 `arg0`, `...``argn`  
 Список указателей на параметры.  
  
 `envp`  
 Массив указателей на параметры среды.  
  
## Возвращаемое значение  
 В случае успешного выполнения эти функции не возвращаются к вызывающему процессу.  Возвращаемое значение, равное \-1, указывает на ошибку; в таком случае устанавливается глобальная переменная `errno`.  
  
|Значение `errno`|Описание|  
|----------------------|--------------|  
|`E2BIG`|Пространство, требуемое для аргументов и параметров среды, превышает 32 КБ.|  
|`EACCES`|Указанный файл имеет нарушение блокировки или общего доступа.|  
|`EINVAL`|Недопустимый параметр.|  
|`EMFILE`|Слишком много открытых файлов.  \(Указанный файл необходимо открыть и определить, является ли он исполняемым.\)|  
|`ENOENT`|Файл или путь не найден.|  
|`ENOEXEC`|Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.|  
|`ENOMEM`|Недостаточно доступной памяти для выполнения нового процесса; либо доступная память повреждена, либо существует недопустимый блок, что указывает на неправильное выделение памяти для процесса, который выполняет вызов.|  
  
 Дополнительные сведения об этих кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Каждая из этих функций загружает и выполняет новый процесс и передает каждый аргумент командной строки как отдельный параметр, а также передает массив указателей на параметры среды.  
  
 Эти функции `_execle` проверяют свои параметры.  Если параметр `cmdname` или `arg0` является нулевым указателем или пустой строкой, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1.  Ни один новый процесс не запущен.  
  
## Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|-------------|----------------------------|------------------------------|  
|`_execle`|\<process.h\>|\<errno.h\>|  
|`_wexecle`|\< process.h \> или \< wchar.h \>|\<errno.h\>|  
  
 Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример в разделе [Функции \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md).  
  
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