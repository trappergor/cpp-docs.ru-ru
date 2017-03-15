---
title: "_tempnam_dbg, _wtempnam_dbg | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wtempnam_dbg
- _tempnam_dbg
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
dev_langs:
- C++
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4f407dce7825a593273206ada02680d6da99e9a0
ms.lasthandoff: 02/24/2017

---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg, _wtempnam_dbg
Версии функции [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md), которые используют отладочную версию`malloc, _malloc_dbg`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_tempnam_dbg(  
   const char *dir,  
   const char *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wtempnam_dbg(  
   const wchar_t *dir,  
   const wchar_t *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dir`  
 Путь, используемый в имени файла, если переменная среды TMP отсутствует или TMP не является допустимым каталогом.  
  
 `prefix`  
 Строка, которая добавляется в начало имен, возвращаемых `_tempnam`.  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или `NULL`.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или `NULL`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая функция возвращает указатель на созданное имя или значение `NULL` в случае сбоя. Сбой может возникнуть, если в переменной среды TMP и в параметре `dir` указано недопустимое имя каталога.  
  
> [!NOTE]
> Не требуется вызывать  `free` (или `free_dbg`) для указателей, выделенных функциями `_tempnam_dbg` и `_wtempnam_dbg`.  
  
## <a name="remarks"></a>Примечания  
 Функции `_tempnam_dbg` и `_wtempnam_dbg` идентичны `_tempnam` и `_wtempnam`, за исключением того, что, если определен `_DEBUG`, эти функции используют отладочную версию `malloc` и `_malloc_dbg` для выделения памяти, если `NULL` передается как первый параметр. Дополнительные сведения см. в разделе [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Как правило, явно вызывать эти функции не требуется. Вместо этого можно определить флаг `_CRTDBG_MAP_ALLOC`. Если определен флаг `_CRTDBG_MAP_ALLOC`, вызовы функций `_tempnam` и `_wtempnam` повторно сопоставляются с `_tempnam_dbg` и `_wtempnam_dbg` соответственно, а для параметра `blockType` задается флаг `_NORMAL_BLOCK`. Таким образом, не требуется явно вызывать эти функции, если только нет необходимости пометить блоки кучи как `_CLIENT_BLOCK`. Дополнительные сведения см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
