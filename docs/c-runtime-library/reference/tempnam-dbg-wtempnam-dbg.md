---
title: "_tempnam_dbg, _wtempnam_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtempnam_dbg"
  - "_tempnam_dbg"
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
  - "wtempnam_dbg"
  - "tempnam_dbg"
  - "_tempnam_dbg"
  - "_wtempnam_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tempnam_dbg - функция"
  - "_wtempnam_dbg - функция"
  - "имена файлов [C++], создание временных"
  - "имена файлов [C++], временные"
  - "tempnam_dbg - функция"
  - "временные файлы, создание"
  - "wtempnam_dbg - функция"
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _tempnam_dbg, _wtempnam_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Версии функции [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md), которые используют отладочную версию `malloc, _malloc_dbg`.  
  
## Синтаксис  
  
```  
char *_tempnam_dbg(    const char *dir,    const char *prefix,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wtempnam_dbg(    const wchar_t *dir,    const wchar_t *prefix,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Параметры  
 `dir`  
 Путь, используемый в имени файла, если переменная среды TMP отсутствует или TMP не является допустимым каталогом.  
  
 `prefix`  
 Строка, которая добавляется в начало имен, возвращаемых `_tempnam`.  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK`или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или `NULL`.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или `NULL`.  
  
## Возвращаемое значение  
 Каждая функция возвращает указатель на созданное имя или значение `NULL` в случае сбоя.  Сбой может возникнуть, если в переменной среды TMP и в параметре `dir` указано недопустимое имя каталога.  
  
> [!NOTE]
>  Не требуется вызывать `free` \(или `free_dbg`\) для указателей, выделенных функциями `_tempnam_dbg` и `_wtempnam_dbg`.  
  
## Заметки  
 Функции `_tempnam_dbg`и `_wtempnam_dbg` идентичны `_tempnam`и `_wtempnam` за исключением того, что если определен флаг `_DEBUG`, эти функции используют отладочную версию `malloc` и `_malloc_dbg` для выделения памяти, если `NULL` передается как первый параметр.  Для получения дополнительной информации см. [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Как правило, явно вызывать эти функции не требуется.  Вместо этого можно определить флаг `_CRTDBG_MAP_ALLOC`.  Если определен флаг `_CRTDBG_MAP_ALLOC`, вызовы функций `_tempnam` и `_wtempnam` повторно сопоставляются с  `_tempnam_dbg` и `_wtempnam_dbg` соответственно, а для параметра `blockType` задается тип `_NORMAL_BLOCK`.  Таким образом, не требуется явно вызывать эти функции, если только нет необходимости пометить блоки кучи как `_CLIENT_BLOCK`.  Для получения дополнительной информации см. [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [Версии отладки функций выделения кучи](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)