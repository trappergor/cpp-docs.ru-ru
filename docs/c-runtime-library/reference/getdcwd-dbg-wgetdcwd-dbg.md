---
title: "_getdcwd_dbg, _wgetdcwd_dbg | Microsoft Docs"
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
  - "_getdcwd_dbg"
  - "_wgetdcwd_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "_getdcwd_dbg"
  - "getdcwd_dbg"
  - "_wgetdcwd_dbg"
  - "wgetdcwd_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getdcwd_dbg - функция"
  - "_wgetdcwd_dbg - функция"
  - "текущая рабочая папка"
  - "каталоги [C++], текущая рабочая"
  - "getdcwd_dbg - функция"
  - "wgetdcwd_dbg - функция"
  - "рабочая папка"
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getdcwd_dbg, _wgetdcwd_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Отладочные версии функций [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md) \(доступны только во время отладки\)  
  
## Синтаксис  
  
```  
char *_getdcwd_dbg(    int drive,    char *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wgetdcwd_dbg(    int drive,    wchar_t *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Параметры  
 `drive`  
 Имя диска.  
  
 `buffer`  
 Место хранения пути.  
  
 `maxlen`  
 Максимальная длина пути в символах: `char` для `_getdcwd_dbg`и `wchar_t`для `_wgetdcwd_dbg`.  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK`или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или `NULL`.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или `NULL`.  
  
## Возвращаемое значение  
 Возвращает указатель на `buffer`.  Возвращаемое значение `NULL` указывает на ошибку, а для `errno` задается значение `ENOMEM`, указывающее на недостаток памяти для выделения `maxlen` байт \(если аргумент `NULL` задан как `buffer`\), или значение `ERANGE`, указывающее, что длина пути превышает `maxlen`.  Для получения дополнительной информации см. [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функции `_getdcwd_dbg` и `_wgetdcwd_dbg` идентичны `_getdcwd` и `_wgetdcwd` за исключением того, что если определен флаг `_DEBUG`, эти функции используют отладочную версию функций `malloc` и `_malloc_dbg` для выделения памяти, если `NULL` передается как параметр `buffer`.  Для получения дополнительной информации см. [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Как правило, явно вызывать эти функции не требуется.  Вместо этого можно определить флаг `_CRTDBG_MAP_ALLOC`.  Если определен флаг `_CRTDBG_MAP_ALLOC`, вызовы функций `_getdcwd` и `_wgetdcwd` повторно сопоставляются с `_getdcwd_dbg` и `_wgetdcwd_dbg` соответственно, а для параметра `blockType` задается тип `_NORMAL_BLOCK`.  Таким образом, не требуется явно вызывать эти функции, если только нет необходимости пометить блоки кучи как `_CLIENT_BLOCK`.  Для получения дополнительной информации см. [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Универсальное текстовое сопоставление функций  
  
|Процедура Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|-----------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tgetdcwd_dbg`|`_getdcwd_dbg`|`_getdcwd_dbg`|`_wgetdcwd_dbg`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_getdcwd_dbg`|\<crtdbg.h\>|  
|`_wgetdcwd_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 <xref:System.Environment.CurrentDirectory%2A?displayProperty=fullName>  
  
## См. также  
 [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)