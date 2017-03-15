---
title: "_spawnlp, _wspawnlp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wspawnlp"
  - "_spawnlp"
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
  - "_wspawnlp"
  - "wspawnlp"
  - "_spawnlp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wspawnlp - функция"
  - "_spawnlp - функция"
  - "процессы, создание"
  - "процессы, выполнение нового"
  - "_wspawnlp - функция"
  - "создание процесса"
  - "spawnlp - функция"
ms.assetid: 74fc6e7a-4f24-4103-9387-7177875875e6
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _spawnlp, _wspawnlp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает и выполняет новый процесс.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
intptr_t _spawnlp(  
   int mode,  
   const char *cmdname,  
   const char *arg0,  
   const char *arg1,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wspawnlp(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   const wchar_t *arg1,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### Параметры  
 `mode`  
 Режим выполнения для вызывающего процесса.  
  
 `cmdname`  
 Путь к выполняемому файлу.  
  
 `arg0, arg1, ... argn`  
 Список указателей на аргументы. Аргумент `arg0` обычно является указателем на параметр `cmdname`. Аргументы `arg1`–`argn` являются указателями на строки символов, которые образуют новый список аргументов. После `argn` должно следовать указатель `NULL`, отмечающий конец списка аргументов.  
  
## Возвращаемое значение  
 Возвращаемое значение синхронных функций `_spawnlp`  или `_wspawnlp`  \(для параметра `mode` указано значение `_P_WAIT` \) — это состояние завершения нового процесса. Возвращаемое значение асинхронной функции `_spawnlp` или `_wspawnlp` \(для параметра `_P_NOWAIT` указано значение `_P_NOWAITO` или `mode`\) — это дескриптор процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Для состояния выхода можно задать ненулевое значение, если порожденный процесс специально вызывает процедуру `exit` с ненулевым аргументом. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение –1 указывает на ошибку \(новый процесс не запущен\). В этом случае `errno` имеет одно из следующих значений.  
  
 `E2BIG`  
 Длина списка аргументов превышает 1024 байта.  
  
 `EINVAL`  
 Недопустимый аргумент `mode`.  
  
 `ENOENT`  
 Файл или путь не найден.  
  
 `ENOEXEC`  
 Указанный файл не является исполняемым или имеет недопустимый формат исполняемого файла.  
  
 `ENOMEM`  
 Недостаточно памяти для выполнения нового процесса.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Каждая из этих функций создает и выполняет новый процесс и передает каждый аргумент командной строки как отдельный параметр, а также использует переменную среды `PATH` для поиска выполняемого файла.  
  
 Эти функции проверяют свои параметры. Если параметр `cmdname` или `arg0` представляет собой пустую строку или указатель NULL, эти функции создают исключение недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1. Нет порожденных новых процессов.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_spawnlp`|\<process.h\>|  
|`_wspawnlp`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример в разделе [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md).  
  
## Эквивалент в .NET Framework  
  
-   [System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [Функции \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)