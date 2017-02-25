---
title: "_spawnve, _wspawnve | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_spawnve"
  - "_wspawnve"
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
  - "wspawnve"
  - "_spawnve"
  - "_wspawnve"
  - "spawnve"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_spawnve - функция"
  - "_wspawnve - функция"
  - "создание процесса"
  - "процессы, создание"
  - "процессы, выполнение нового"
  - "spawnve - функция"
  - "wspawnve - функция"
ms.assetid: 26d1713d-b551-4f21-a07b-e9891a2ae6cf
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _spawnve, _wspawnve
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает и выполняет новый процесс.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
intptr_t _spawnve(  
   int mode,  
   const char *cmdname,  
   const char *const *argv,  
   const char *const *envp   
);  
intptr_t _wspawnve(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *const *argv,  
   const wchar_t *const *envp   
);  
```  
  
#### Параметры  
 `mode`  
 Режим выполнения для вызывающего процесса.  
  
 `cmdname`  
 Путь к выполняемому файлу.  
  
 `argv`  
 Массив указателей на аргументы.  Аргумент `argv`\[0\] обычно является указателем на путь в реальном режиме или на название программы в защищенном режиме, а аргументы с `argv`\[1\] по `argv`\[`n`\] — указатели на символьные строки, формирующие новый список аргументов.  Аргумент `argv`\[`n` \+1\] должен быть указателем `NULL`, отмечающим конец списка аргументов.  
  
 `envp`  
 Массив указателей на параметры среды.  
  
## Возвращаемое значение  
 Возвращаемое значение синхронных `_spawnve` или `_wspawnve` \(`_P_WAIT` указано для `mode`\) — статус завершения нового процесса.  Возвращаемое значение асинхронного `_spawnve` или `_wspawnve` \(`_P_NOWAIT` или `_P_NOWAITO` указаны для `mode`\) — дескриптор процесса.  Состояние выхода имеет значение 0, если процесс завершился обычным образом.  Для состояния выхода можно задать ненулевое значение, если порожденный процесс специально вызывает процедуру `exit` с ненулевым аргументом.  Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию.  Возвращаемое значение –1 указывает на ошибку \(новый процесс не запущен\).  В этом случае `errno` имеет одно из следующих значений.  
  
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
 Каждая из этих функций создает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки и массив указателей на параметры среды.  
  
 Эти функции проверяют свои параметры.  Если или `cmdname`, или `argv` — нулевой указатель, или если `argv` указывает на нулевой указатель, или `argv[0]` — пустая строка, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1.  Нет порожденных новых процессов.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_spawnve`|\<stdio.h\> или \<process.h\>|  
|`_wspawnve`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример в разделе [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md).  
  
## Эквивалент в .NET Framework  
  
-   [Класс System::Diagnostics::Process](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
-   [Класс System::Diagnostics::ProcessStartInfo](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
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