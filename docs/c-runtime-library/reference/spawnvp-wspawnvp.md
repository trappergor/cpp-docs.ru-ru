---
title: "_spawnvp, _wspawnvp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wspawnvp"
  - "_spawnvp"
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
  - "_wspawnvp"
  - "_spawnvp"
  - "wspawnvp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wspawnvp - функция"
  - "процессы, создание"
  - "_wspawnvp - функция"
  - "процессы, выполнение нового"
  - "spawnvp - функция"
  - "создание процесса"
  - "_spawnvp - функция"
ms.assetid: 8d8774ec-6ad4-4680-a5aa-440cde1e0249
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _spawnvp, _wspawnvp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает и выполняет процесс.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
intptr_t _spawnvp(  
   int mode,  
   const char *cmdname,  
   const char *const *argv   
);  
intptr_t _wspawnvp(  
   int mode,  
   const wchar_t *cmdname,  
   const wchar_t *const *argv   
);  
```  
  
#### Параметры  
 `mode`  
 Режим выполнения для вызова процесса.  
  
 `cmdname`  
 Путь к выполняемому файлу.  
  
 `argv`  
 Массив указателей на аргументы. Аргумент `argv`\[0\] обычно является указателем на путь в реальном режиме или на имя программы в защищенном режиме, а аргументы с `argv`\[1\] по `argv`\[`n`\] — это указатели на символьные строки, формирующие новый список аргументов. Аргумент `argv`\[`n` \+1\] должен быть указателем `NULL`, отмечающим конец списка аргументов.  
  
## Возвращаемое значение  
 Возвращаемое значение синхронных функций `_spawnvp` или `_wspawnvp` \(для параметра `_P_WAIT` указано значение `mode`\) — это состояние завершения нового процесса. Возвращаемое значение асинхронной функции `_spawnvp` или `_wspawnvp` \(для параметра `_P_NOWAIT` указано значение `_P_NOWAITO` или `mode`\) — это дескриптор процесса. Состояние выхода имеет значение 0, если процесс завершился обычным образом. Для состояния выхода можно задать ненулевое значение, если порожденный процесс использует ненулевой аргумент для вызова процедуры `exit`. Если новый процесс не задал положительное состояние выхода в явном виде, положительное состояние выхода указывает на аварийный выход по отмене или прерыванию. Возвращаемое значение –1 указывает на ошибку \(новый процесс не запущен\). В этом случае `errno` имеет одно из следующих значений:  
  
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
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Каждая из этих функций создает и выполняет новый процесс, передавая ему массив указателей на аргументы командной строки и используя для поиска файла, который необходимо выполнить, переменную среды `PATH`.  
  
 Эти функции проверяют свои параметры. Если параметр `cmdname` или `argv` является указателем NULL, параметр `argv` указывает на указатель NULL или параметр `argv[0]` является пустой строкой, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают \-1. Нет порожденных новых процессов.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_spawnvp`|\<stdio.h\> или \<process.h\>|  
|`_wspawnvp`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
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