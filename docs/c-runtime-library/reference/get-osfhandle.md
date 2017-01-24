---
title: "_get_osfhandle | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_osfhandle"
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
  - "get_osfhandle"
  - "_get_osfhandle"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "операционные системы, получение дескрипторов файлов"
  - "Функция get_osfhandle"
  - "Функция _get_osfhandle"
  - "дескрипторы файлов [C++], операционная система"
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает дескриптор файла операционной системы, связанный с указанным дескриптором файла.  
  
## Синтаксис  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
#### Параметры  
 `fd`  
 Дескриптор существующего файла.  
  
## Возвращаемое значение  
 Дескриптор файла операционной системы, если `fd` допустим.  В противном случае, вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если разрешено продолжение выполнения, то эта функция возвращает `INVALID_HANDLE_VALUE` \(– 1\) и устанавливает `errno` в `EBADF`, что указывает на недопустимый дескриптор файла.  
  
## Заметки  
 Чтобы закрыть файл, открытый `_get_osfhandle`, вызовите `_close`.  Базовый дескриптор также можно закрыть вызовом `_close`, поэтому не нужно вызывать функцию `CloseHandle` Win32 для исходного дескриптора.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_get_osfhandle`|\<io.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_close](../Topic/_close.md)   
 [Функция \_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)