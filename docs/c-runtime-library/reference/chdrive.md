---
title: "_chdrive | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_chdrive"
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
  - "chdrive"
  - "_chdrive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_chdrive - функция"
  - "chdrive - функция"
  - "диски, изменение"
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _chdrive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Изменяет текущий рабочий диск.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _chdrive(   
   int drive   
);  
```  
  
#### Параметры  
 `drive`  
 Целое число от 1 до 26, определяющее текущий рабочий диск \(1\=A, 2\=B и т д\).  
  
## Возвращаемое значение  
 Ноль \(0\), если текущий рабочий диск был успешно изменен; в противном случае — значение \-1.  
  
## Заметки  
 Если `drive` не находится в диапазоне от 1 до 26, то вызывается обработчик недопустимого параметра как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если разрешено продолжение выполнения, функция **\_chdrive** возвращает \-1, `errno` устанавливается в `EACCES`, а `_doserrno` устанавливается в `ERROR_INVALID_DRIVE`.  
  
 Функция **\_chdrive** не потокобезопасна, поскольку она зависит от функции **SetCurrentDirectory**, которая сама по себе не потокобезопасна.  Для безопасного использования **\_chdrive** в многопоточном приложении необходимо предоставить собственную синхронизацию потока.  Дополнительные сведения см. в [Библиотека MSDN](http://go.microsoft.com/fwlink/?LinkID=150542) с поисковым параметром **SetCurrentDirectory**.  
  
 Функция **\_chdrive** изменяет только текущий рабочий диск; **\_chdir** изменяет текущую рабочую папку.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|**\_chdrive**|\<direct.h\>|  
  
 Для получения дополнительной информации см. [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример в разделе [\_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## Эквивалент в .NET Framework  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## См. также  
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../Topic/_chdir,%20_wchdir.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir, \_wmkdir](../Topic/_mkdir,%20_wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)