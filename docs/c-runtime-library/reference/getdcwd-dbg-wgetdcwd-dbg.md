---
title: "_getdcwd_dbg, _wgetdcwd_dbg | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
- _getdcwd_dbg
- getdcwd_dbg
- _wgetdcwd_dbg
- wgetdcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
caps.latest.revision: 14
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 9131d9769d96d7668db180c5c9595ea786770e8b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="getdcwddbg-wgetdcwddbg"></a>_getdcwd_dbg, _wgetdcwd_dbg
Отладочные версии функций [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md) (доступны только во время отладки).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_getdcwd_dbg(  
   int drive,  
   char *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wgetdcwd_dbg(  
   int drive,  
   wchar_t *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `drive`  
 Имя диска.  
  
 `buffer`  
 Место хранения пути.  
  
 `maxlen`  
 Максимальная длина пути в символах: `char` для `_getdcwd_dbg` и `wchar_t` для `_wgetdcwd_dbg`.  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла, который запросил операцию выделения, или `NULL`.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой была запрошена операция выделения, или `NULL`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на `buffer`. Возвращаемое значение `NULL` указывает на ошибку, а для `errno` задается значение `ENOMEM`, указывающее на недостаток памяти для выделения `maxlen` байт (если аргумент `NULL` задан как `buffer`), или значение `ERANGE`, указывающее, что длина пути превышает `maxlen` . Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функции `_getdcwd_dbg` и `_wgetdcwd_dbg` идентичны `_getdcwd` и `_wgetdcwd` за исключением того, что если определен флаг `_DEBUG`, эти функции используют отладочную версию функций `malloc` и `_malloc_dbg` для выделения памяти, если `NULL` передается как параметр `buffer`. Дополнительные сведения см. в разделе [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Как правило, явно вызывать эти функции не требуется. Вместо этого можно определить флаг `_CRTDBG_MAP_ALLOC`. Если определен флаг `_CRTDBG_MAP_ALLOC`, вызовы функций `_getdcwd` и `_wgetdcwd` повторно сопоставляются с `_getdcwd_dbg` и `_wgetdcwd_dbg` соответственно, а для параметра `blockType` задается тип `_NORMAL_BLOCK`. Таким образом, не требуется явно вызывать эти функции, если только нет необходимости пометить блоки кучи как `_CLIENT_BLOCK`. Дополнительные сведения см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd_dbg`|`_getdcwd_dbg`|`_getdcwd_dbg`|`_wgetdcwd_dbg`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_getdcwd_dbg`|\<crtdbg.h>|  
|`_wgetdcwd_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)
