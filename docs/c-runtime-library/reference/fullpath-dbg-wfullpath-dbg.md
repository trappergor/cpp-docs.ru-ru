---
title: "_fullpath_dbg, _wfullpath_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wfullpath_dbg"
  - "_fullpath_dbg"
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
  - "wfullpath_dbg"
  - "_wfullpath_dbg"
  - "_fullpath_dbg"
  - "fullpath_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fullpath_dbg - функция"
  - "_wfullpath_dbg - функция"
  - "абсолютные пути"
  - "fullpath_dbg - функция"
  - "относительные пути к файлам"
  - "wfullpath_dbg - функция"
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _fullpath_dbg, _wfullpath_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Версии [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md), которые используют отладочную версию `malloc` для выделения памяти.  
  
## Синтаксис  
  
```  
char *_fullpath_dbg(     char *absPath,    const char *relPath,    size_t maxLength,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wfullpath_dbg(     wchar_t *absPath,    const wchar_t *relPath,    size_t maxLength,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Параметры  
 `absPath`  
 Указатель на буфер, содержащий абсолютный или полный путь, или значение `NULL`.  
  
 `relPath`  
 Относительный путь.  
  
 `maxLength`  
 Максимальная длина буфера абсолютного пути \(`absPath`\).  Длина указывается в байтах для `_fullpath` и в расширенных символах \(`wchar_t`\) для `_wfullpath`.  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или `NULL`.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или `NULL`.  
  
## Возвращаемое значение  
 Каждая функция возвращает указатель на буфер, который содержит абсолютный путь \(`absPath`\).  При наличии ошибки \(например, если значение, передаваемое в `relPath`, включает недопустимую букву диска или букву диска, которую не удается найти, или если длина созданного абсолютного пути \(`absPath`\) превышает `maxLength`\), функция возвращает значение `NULL`.  
  
## Заметки  
 Функции `_fullpath_dbg` и `_wfullpath_dbg` идентичны `_fullpath` и `_wfullpath` за исключением того, что если определен флаг **\_**`DEBUG`, эти функции используют отладочную версию функций `malloc` и `_malloc_dbg` для выделения памяти, если NULL передается как первый параметр.  Сведения о компонентах отладки `_malloc_dbg` см. в разделе [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Как правило, явно вызывать эти функции не требуется.  Вместо этого можно определить флаг `_CRTDBG_MAP_ALLOC`.  Если определен флаг `_CRTDBG_MAP_ALLOC`, вызовы функций `_fullpath` и `_wfullpath`повторно сопоставляются с `_fullpath_dbg` и `_wfullpath_dbg` соответственно, а для параметра `blockType` задается тип `_NORMAL_BLOCK`.  Таким образом, не требуется явно вызывать эти функции, если только нет необходимости пометить блоки кучи как `_CLIENT_BLOCK`.  Для получения дополнительной информации см. [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Универсальное текстовое сопоставление функций  
  
|Процедура Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|-----------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tfullpath_dbg`|`_fullpath_dbg`|`_fullpath_dbg`|`_wfullpath_dbg`|  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_fullpath_dbg`|\<crtdbg.h\>|  
|`_wfullpath_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 <xref:System.IO.File.Create%2A>  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)