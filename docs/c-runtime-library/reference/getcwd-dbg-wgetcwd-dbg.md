---
title: "_getcwd_dbg, _wgetcwd_dbg | Microsoft Docs"
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
  - "_wgetcwd_dbg"
  - "_getcwd_dbg"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getcwd_dbg"
  - "_wgetcwd_dbg"
  - "getcwd_dbg"
  - "wgetcwd_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getcwd_dbg - функция"
  - "_wgetcwd_dbg - функция"
  - "текущая рабочая папка"
  - "каталоги [C++], текущая рабочая"
  - "getcwd_dbg - функция"
  - "wgetcwd_dbg - функция"
  - "рабочая папка"
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getcwd_dbg, _wgetcwd_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Отладочные версии функций [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md) \(доступны только во время отладки\)  
  
## Синтаксис  
  
```  
char *_getcwd_dbg(     char *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wgetcwd_dbg(     wchar_t *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Параметры  
 `buffer`  
 Место хранения пути.  
  
 `maxlen`  
 Максимальная длина пути в символах: `char` для `_getcwd_dbg` и `wchar_t` для `_wgetcwd_dbg`.  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или `NULL`.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или `NULL`.  
  
## Возвращаемое значение  
 Возвращает указатель на `buffer`.  Возвращаемое значение `NULL` указывает на ошибку, а для `errno` задается значение `ENOMEM`, указывающее на недостаток памяти для выделения `maxlen` байт \(если аргумент `NULL` задан как `buffer`\), или значение `ERANGE`, указывающее, что длина пути превышает `maxlen`.  
  
 Для получения дополнительной информации см. [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функции `_getcwd_dbg` и `_wgetcwd_dbg` идентичны `_getcwd` и `_wgetcwd` за исключением того, что если определен флаг \_`DEBUG`, эти функции используют отладочную версию функций `malloc` и `_malloc_dbg` для выделения памяти, если `NULL` передается как первый параметр.  Для получения дополнительной информации см. [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Как правило, явно вызывать эти функции не требуется.  Вместо этого можно определить флаг `_CRTDBG_MAP_ALLOC`.  Если определен флаг `_CRTDBG_MAP_ALLOC`, вызовы функций `_getcwd`и `_wgetcwd`повторно сопоставляются с `_getcwd_dbg`и `_wgetcwd_dbg` соответственно, а для параметра `blockType` задается тип `_NORMAL_BLOCK`.  Таким образом, не требуется явно вызывать эти функции, если только нет необходимости пометить блоки кучи как `_CLIENT_BLOCK`.  Для получения дополнительной информации см. [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
## Универсальное текстовое сопоставление функций  
  
|Процедура Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|-----------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tgetcwd_dbg`|`_getcwd_dbg`|`_getcwd_dbg`|`_wgetcwd_dbg`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_getcwd_dbg`|\<crtdbg.h\>|  
|`_wgetcwd_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 <xref:System.Environment.CurrentDirectory%2A>  
  
## См. также  
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)